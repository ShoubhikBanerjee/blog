---
title: "Managing EKS Pod Identities at Scale: A GitOps Approach with Argo CD and AWS ACK"
description: "Learn how to efficiently manage Amazon EKS Pod Identity associations at scale
using GitOps practices with Argo CD and AWS Controllers for Kubernetes (ACK). This comprehensive
guide addresses the critical challenge of eventual consistency in the EKS Pod Identity API and
provides robust solutions for production deployments."
date: 2025-10-26T13:14:43.609547+05:30
tags: [AWS, EKS, GitOps, ArgoCD, Kubernetes, DevOps, CloudNative, IAM, PodIdentity, ACK]
categories: [DevOps, AWS, Kubernetes]
image: "https://aws.amazon.com/blogs/containers/how-to-manage-eks-pod-identities-at-scale-using-argo-cd-and-aws-ack/"
math: false
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# 🚀 Managing EKS Pod Identities at Scale: A GitOps Approach with Argo CD and AWS ACK
💡 **Introduction**: Learn how to efficiently manage Amazon EKS Pod Identity associations at
scale using GitOps practices with Argo CD and AWS Controllers for Kubernetes (ACK). This
comprehensive guide addresses the critical challenge of eventual consistency in the EKS Pod
Identity API and provides robust solutions for production deployments.
---
## 🎯 Understanding the Challenge
### What is GitOps?
GitOps represents a modern approach to continuous delivery that leverages Git as the single
source of truth for declarative infrastructure and applications. **Argo CD** serves as a
powerful tool enabling teams to implement GitOps workflows that significantly enhance
development and deployment processes. This approach enables organizations to achieve faster,
more reliable deployments while maintaining a clear audit trail of all changes through Git
history.
### 🔐 EKS Pod Identity: Streamlining IAM for Kubernetes
**Amazon EKS Pod Identity** introduces a streamlined approach to managing AWS Identity and
Access Management (IAM) permissions for applications running on Amazon EKS clusters. This
feature addresses key challenges in managing permissions across multiple EKS clusters, offering
significant advantages over the traditional IAM Roles for Service Accounts (IRSA) method,
particularly in GitOps workflows.
**Key Benefits:**
  - ✅ Maintains principle of least privilege with fine-grained pod-level control
  - 🛡️ Improves security by reducing potential attack surface compared to node-level permission
  - 🔄 Seamless integration with EKS clusters running Kubernetes version 1.24+
  - 🏗️ Works out-of-the-box with existing AWS services and SDK
---
## 🧩 AWS Controllers for Kubernetes (ACK) Overview
The **AWS Controllers for Kubernetes (ACK)** provides a set of custom controllers that enable
management of AWS resources directly through Kubernetes custom resources. This powerful tool
offers:
  - 🎛️ Kubernetes-native management of AWS services using Custom Resource Definitions (CRDs
  - 🔄 Controllers that reconcile desired state in Kubernetes with actual AWS resources
  - 🌐 Support for numerous AWS services including Amazon EKS, S3, RDS, and more
In this implementation, we utilize the **ACK service controller for Amazon EKS** to manage EKS
Pod Identity associations, enabling pods to assume IAM roles through Kubernetes service
accounts.
---
## 🏗️ Implementation Architectur
### High-Level Process Flow
| Step | Component | Action | Purpose |
|------|-----------|--------|---------|
| 1 | EKS Pod Identity Agent | Installation | Provides credential management on nodes |
| 2 | ACK Controller | Deployment | Manages Pod Identity associations |
| 3 | Validation Job | Execution | Ensures role association before app deployment |
| 4 | Application Pods | Deployment | Runs with correct IAM permissions |
---
## 🛠️ Step-by-Step Implementatio
### Prerequisites Checklist
  - ✅ AWS CLI installed
  - ✅ kubectl (Kubernetes command line tool) installed
  - ✅ jq tool installed
  - ✅ Helm CLI installed
  - ✅ Access to existing EKS cluster with Argo CD installed
### 1️⃣ Install Amazon EKS Pod Identity Agen
The Pod Identity Agent runs as a Kubernetes DaemonSet and provides credentials exclusively to
pods on its node:
```bash
   # Verify cluster connection
   eval "$(terraform output -raw configure_kubectl)"
   kubectl get pods -A

   # Install the Pod Identity Agent add-on
   aws eks create-addon \
     --cluster-name getting-started-gitops \
     --addon-name eks-pod-identity-agent \
     --addon-version v1.3.9-eksbuild.1
```
> **Note**: EKS Auto Mode Clusters have this capability built-in and don't require manual
installation.
### 2️⃣ Create IAM Role and Install ACK Controlle
#### Create the ACK Controller Role
```bash
   # Create trust policy
   cat <<EOF > trust-policy.json
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Effect": "Allow",
         "Principal": {
           "Service": "pods.eks.amazonaws.com"
         },
         "Action": [
           "sts:AssumeRole",
           "sts:TagSession"
         ]
       }
     ]
   }
   EOF

   # Create IAM role
   export ACKROLE=sample-argocd-ack-eks-ackrole
   aws iam create-role \
     --role-name $ACKROLE \
     --assume-role-policy-document file://trust-policy.json

   # Create inline policy for Pod Identity associations
   cat <<EOF > policy.json
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Sid": "ackekspodidentitypolicy",
         "Effect": "Allow",
         "Action": [
           "eks:CreatePodIdentityAssociation",
           "eks:TagResource"
         ],
         "Resource": "arn:aws:eks:us-west-2:123456789012:cluster/getting-started-gitops"
       },
       {
         "Sid": "ackekspodidentitypolicytag",
         "Effect": "Allow",
         "Action": [
           "eks:DescribePodIdentityAssociation",
           "eks:DeletePodIdentityAssociation",
           "eks:TagResource"
         ],
         "Resource":
   "arn:aws:eks:us-west-2:123456789012:podidentityassociation/getting-started-gitops/*"
       },
       {
         "Sid": "PassRoleToACKEksRole",
         "Effect": "Allow",
         "Action": [
           "iam:PassRole",
           "iam:GetRole"
         ],
         "Resource": "arn:aws:iam::123456789012:role/sample-argocd-ack-eks-role"
       }
     ]
   }
   EOF

   aws iam put-role-policy \
     --role-name $ACKROLE \
     --policy-name "ack-eks-podidentity-policy" \
     --policy-document file://policy.json
```
#### Install ACK Controller with Helm
```bash
   export SERVICE=eks
   export RELEASE_VERSION=$(curl -sL
   https://api.github.com/repos/aws-controllers-k8s/${SERVICE}-controller/releases/latest | jq -r
   '.tag_name | ltrimstr("v")')
   export ACK_SYSTEM_NAMESPACE=ack-system
   export AWS_REGION=us-west-2

   aws ecr-public get-login-password --region us-east-1 | \
     helm registry login --username AWS --password-stdin public.ecr.aws

   helm install --create-namespace -n $ACK_SYSTEM_NAMESPACE ack-$SERVICE-controller \
     oci://public.ecr.aws/aws-controllers-k8s/$SERVICE-chart \
     --version=$RELEASE_VERSION \
     --set=aws.region=$AWS_REGION
```
---
## ⚠️ The Eventual Consistency Challenge
### Problem Identification
Due to the **eventually consistent nature** of the EKS Pod Identity API, combined with
automation speed, applications may encounter failures when associating roles with service
accounts. This can result in:
  - 🚨 Pods receiving node group role instead of intended Pod Identity role
  - 📊 Multiple disruptions per day at scale
  - 💥 Application deployment failures
### 🏥 Solution: Validation Job Pattern
The most effective solution involves implementing a **validation job** that verifies the EKS Pod
Identity association before deploying application workloads.
#### Validation Job Implementation
```yaml
   apiVersion: batch/v1
   kind: Job
   metadata:
     labels:
       app: argo-ack-eks-static
     name: argo-ack-eks-static
     annotations:
       helm.sh/hook-weight: "50"
   spec:
     template:
       spec:
         serviceAccountName: argo-ack-eks-static
         restartPolicy: Never
         containers:
         - name: argo-ack-eks
           image: {{ .Values.image }}
           env:
           - name: EXPECTED_ASSUMED_ROLE_ARN
             value: {{ regexReplaceAll ":role/" .Values.roleArn ":assumed-role/" }}
           command:
           - sh
           - "-c"
           - |
             env | grep AWS_CONTAINER
             if [ $? -ne 0 ]; then
               echo 'No AWS environment variables set'
               exit 1
             else
               echo 'AWS environment found'
               env
             fi
             aws sts get-caller-identity --output text --query "Arn" | grep -qi
   "$EXPECTED_ASSUMED_ROLE_ARN"
             if [ $? -eq 0 ]; then
               echo "Correct role association verified"
             else
               echo "Role association failed"
               exit 1
             fi
     backoffLimit: 4
     activeDeadlineSeconds: 60
```
---
## 📋 Deployment Orchestration
### Helm Hook Weight Strategy
| Weight | Component | Purpose |
|--------|-----------|---------|
| -50 | Service Account & Pod Identity Association | Create foundational resources |
| 50 | Validation Job | Verify role association |
| 100 | Application Deployment | Deploy with confirmed permissions |
This orchestration ensures:
  - 🔄 **Sequential deployment** with proper dependency management
  - ✅ **Validation gates** preventing deployment with incorrect permissions
  - 🛡️ **Automatic retry** mechanisms for transient failure
---
## 🎯 Alternative Solutions
### Sync Wave Delay Adjustment
Argo CD allows control over deployment order through sync waves with a default 2-second delay.
While increasing the `ARGOCD_SYNC_WAVE_DELAY` can reduce failures, it has drawbacks:
**Pros:**
  - ✅ Simple implementation
  - ✅ May reduce some failure scenarios
**Cons:**
  - ❌ Slows down ALL deployments globally
  - ❌ Not targeted to Pod Identity specific issues
  - ❌ May not be suitable for all environments
---
## 🧹 Cleanup Process
### Complete Resource Cleanup
```bash
   # Delete Argo CD application
   kubectl delete -f application-with-job.yaml

   # Remove IAM roles
   aws iam delete-role --role-name sample-argocd-ack-eks-role
   aws iam delete-role-policy --role-name sample-argocd-ack-eks-ackrole --policy-name
   ack-eks-podidentity-policy
   aws iam delete-role --role-name sample-argocd-ack-eks-ackrole

   # Uninstall ACK controller
   helm uninstall -n $ACK_SYSTEM_NAMESPACE ack-$SERVICE-controller

   # Remove Pod Identity Agent
   aws eks delete-addon --cluster-name getting-started-gitops --addon-name eks-pod-identity-agent
```
---
## ✨ Key Takeaways
### 🎯 **Solution Comparison**
| Approach | Effectiveness | Impact on Other Deployments | Production Ready |
|----------|---------------|------------------------------|------------------|
| **Validation Job** | ⭐⭐⭐⭐⭐ | ✅ No impact | ✅ Yes |
| **Sync Wave Delay** | ⭐⭐⭐ | ❌ Slows all deployments | ⚠️ Limited |
### 🚀 **Best Practices**
1. **Implement validation jobs** for production environments requiring reliable Pod Identity
associations
2. **Use proper hook weights** to ensure correct deployment sequencing
3. **Monitor job completion** before proceeding with application deployment
4. **Maintain GitOps principles** throughout the automation process
### 🔮 **Future Considerations**
As organizations scale their container deployments, the validation job pattern provides a
robust, targeted solution that doesn't impact other deployment workflows. This approach
maintains the benefits of GitOps while addressing the specific challenges of eventual
consistency in cloud APIs.
---
*How are you currently handling IAM role associations in your Kubernetes deployments, and what
challenges have you encountered with eventual consistency?*
---
*Credits: Originally posted here: https://aws.amazon.com/blogs/containers/how-to-manage-eks-pod-
identities-at-scale-using-argo-cd-and-aws-ack/*
#AWS #EKS #GitOps #ArgoCD #Kubernetes #DevOps #CloudNative #IAM #PodIdentity #ACK