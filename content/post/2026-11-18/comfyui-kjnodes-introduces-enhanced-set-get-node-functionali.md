---
title: "ComfyUI-KJNodes Introduces Enhanced Set/Get Node Functionality"
slug: "comfyui-kjnodes-introduces-enhanced-set-get-node-functionality"
description: "The ComfyUI-KJNodes project has recently undergone a significant update, introducing enhanced functionalities for Set/Get nodes within the ComfyUI framework. This update focuses on extending support..."
date: 2026-11-18T18:09:03+05:30
tags: [ComfyUI, AIToolkit, KJNodes, SetGetNodes, Subgraphs, NodeOptimization]
categories: ["AI", "AI Development Tools", "Node-based Interfaces", "Software Updates", "Python Development"]
image: "https://avatars.githubusercontent.com/u/40791699?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# ComfyUI-KJNodes Introduces Enhanced Set/Get Node Functionality

## 🔍 Overview
The ComfyUI-KJNodes project has recently undergone a significant update, introducing enhanced functionalities for Set/Get nodes within the ComfyUI framework. This update focuses on extending support to both legacy and nodes 2.0, alongside promoting cross-subgraph interconnectivity.

## ⚙️ Key Details
- **Backward Compatibility**: The rewrite maintains compatibility with earlier versions, ensuring seamless integration with existing workflows.
- **Subgraph Functionality**: Set/Get nodes now operate across parent and child subgraphs, facilitating broader interactions within multi-tiered structures.
- **New Operations**:
  - Convert link to Set/Get using a right-click on any link midpoint.
  - Batch convert selected node outputs to Set/Get pairs.
  - The canvas right-click menu supports the conversion of outputs on selected nodes.
- **Key Shortcuts**:
  - `Ctrl+Shift+S`: Add Set nodes.
  - `Ctrl+Shift+G`: Add Get nodes.
  - `Ctrl+Shift+L`: Toggle visibility of all connections.
- **Settings Enhancements**: New settings for managing link visibility, keyboard shortcuts without conflicting with other actions, and sprite appearance based on connections.
- **Conversion Features**: Right-clicking a SetNode adds a corresponding GetNode, and double-clicking a GetNode navigates to its paired SetNode.
- **Type and Color Update**: Nodes now reflect type changes when inputs or outputs are disconnected, ensuring consistency in visual feedback.
- **Settings Structure**: Settings have been reorganized under KJNodes > Set & Get and KJNodes > General categories for improved navigation.

## 💡 Why It Matters
This update enhances user interaction and workflow efficiency within the ComfyUI ecosystem. The integration of Set/Get functionalities across subgraphs and the addition of user-friendly features signifies an advancement in customization capabilities, empowering users to build more complex and interconnected AI pipelines.

## 🚀 Availability
To begin using these features, users should:
1. Clone the custom_nodes repo to the `custom_nodes` folder.
2. Install dependencies using `pip install -r requirements.txt`.

For portable installs, utilize:
```bash
custom_setup/ComfyUI_windows_portable-folder/python_embeded/python.exe -m pip install -r ComfyUI/custom_nodes/ComfyUI-KJNodes/requirements.txt
```



#ComfyUI #AIToolkit #KJNodes #SetGetNodes #Subgraphs #NodeOptimization

---

*Source: [kijai/ComfyUI-KJNodes](https://github.com/kijai/ComfyUI-KJNodes)*
