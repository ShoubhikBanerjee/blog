---
title: "AI‑Powered CLI Pipeline Generates Custom PDFs for Job Applications"
slug: "aipowered-cli-pipeline-generates-custom-pdfs-for-job-applications"
description: "Um conjunto de agentes de IA (CrewAI + AWS Bedrock/Claude) lê a descrição de uma vaga e a base profissional da pessoa e gera currículos personalizados em PDF/LaTeX, em PT ou EN, sem inventar..."
date: 2026-11-04T22:02:53+05:30
tags: [AIAgents, ResumeAutomation, CLI, CareerTech]
categories: ["AI", "Artificial Intelligence", "Automation", "Career Development", "Software Tools"]
image: "https://avatars.githubusercontent.com/u/141029718?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# AI‑Powered CLI Pipeline Generates Custom PDFs for Job Applications

Um conjunto de agentes de IA (CrewAI + AWS Bedrock/Claude) lê a descrição de uma vaga e a base profissional da pessoa e gera currículos personalizados em PDF/LaTeX, em PT ou EN, sem inventar informações e preservando toda a trajetória de carreira. O autor, profissional de TI com mais de 30 anos de carreira, usou o método e foi contratado 5 meses depois.

## 🔍 Overview
- Ferramenta: CLI com agentes de IA que automatiza a parte mais trabalhosa do método, produzindo currículos sob medida para cada vaga.
- Método: passo a passo que organiza a busca, da construção do perfil às retrospectivas que refinam o processo.
- Abordagem: tratado como um pipeline de dados, em que cada etapa recebe a saída da anterior.

## 🧩 How it Works
- Cria‑se um arquivo `profile_truth.md` contendo a versão longa e honesta da carreira.
- Todo currículo e toda resposta de entrevista são gerados a partir desse arquivo.
- A IA propõe reordenação, resumo e tradução; o usuário decide o que usar.
- A IA **não pode inventar** informações; nada sai com o seu nome sem você ler.
- Uma planilha simples rastreia quais currículos e fontes de vagas geram respostas.
- Ao fim de cada prazo definido, uma retrospectiva transforma os dados coletados em ajustes no processo.
- Duas trilhas seguem o mesmo método; a diferença está em quem produz o currículo (prompts em chat de IA vs. CLI que gera os arquivos).

## ⚙️ Key Details
- **Requisitos de ambiente**
  - Assistente de IA
  - Python 3.9+ (ou Python 3.12) 
  - LaTeX para gerar PDFs
  - Chave de API de um provedor de IA
- **Segurança**
  - Diretórios `input/`, `data/`, `outputs/` e `privado/` estão no `.gitignore`.
  - Chaves de API ficam somente no `.env`, que também é ignorado pelo git.
  - Senhas, documentos e dados bancários nunca entram em prompts.
- **Limitações da CLI**
  - Cobre apenas parte do método; não busca nem tria vagas.
  - Usa prompts prontos em um chat de IA para gerar o conteúdo.
- **Funções automáticas**
  - Revisão de cobertura automática por posição; prompt disponível para identificar lacunas da vaga.
  - Preparação de entrevista com rascunho automático.
- **Avisos**
  - A IA pode errar datas, exagerar resultados e trocar números.
  - O projeto não serve para fabricar experiência, burlar triagem ou candidatar‑se em massa sem ler as vagas.
- **Documentação**
  - Tutorial completo em `meu-emprego-novo-pipeline/README.md`.

## 🚀 Availability
- O código está organizado em pastas (`input/`, `data/`, `outputs/`, `privado/`) protegidas por `.gitignore`.
- O usuário executa um comando que dispara os agentes e gera os arquivos de currículo.
- As duas trilhas (uso de prompts vs. CLI) utilizam o mesmo perfil‑mestre escrito em `profile_truth.md`.

## 💡 Why it Matters
- Gera currículos personalizados sem inventar informações, preservando a integridade da carreira.
- Automatiza a parte mais trabalhosa da preparação de candidatura, permitindo foco na revisão e no ajuste contínuo.
- Fornece métricas simples (planilha) para avaliar quais abordagens geram respostas, apoiando decisões baseadas em dados.

#AIAgents #ResumeAutomation #CLI #CareerTech

---

*Source: [R238Company/meu-emprego-novo](https://github.com/R238Company/meu-emprego-novo)*
