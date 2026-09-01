---
title: "Omarchy: A New Arch-Based Linux Distribution with Hyprland"
description: "A new Arch-based Linux distribution, Omarchy, has been introduced, offering a complete, opinionated desktop experience with minimal configuration overhead."
date: 2026-09-01T18:06:33+05:30
tags: [Linux, ArchLinux, Hyprland, Omarchy, Wayland, DesktopEnvironment]
categories: [AI]
image: "https://addrom.com/wp-content/uploads/2026/09/omarchy-linux.webp"
author: "Shoubhik Banerjee"
draft: false
---

# Omarchy: A New Arch-Based Linux Distribution with Hyprland

A new Arch-based Linux distribution, Omarchy, has been introduced, offering a complete, opinionated desktop experience with minimal configuration overhead.

## 🔍 Overview
- Omarchy is an Arch-based Linux distribution designed to deliver a complete, opinionated desktop experience without the usual configuration overhead.
- It combines Arch Linux, the Hyprland tiling Wayland compositor, and Quickshell for the status bar, launcher, notifications, and other desktop components.
- The project is created and maintained by David Heinemeier Hansson.

## ⚙️ Key details
- Omarchy ships with development and productivity tools such as Neovim, Chromium, LibreOffice, Obsidian, and Spotify.
- It includes full-disk encryption by default, Btrfs with Snapper snapshots, UFW firewall, and a collection of synchronized themes that can be switched instantly.
- It embraces Arch Linux as the foundation, providing access to the full Arch ecosystem, the AUR, and rolling updates.
- The desktop experience centers on keyboard-driven workflows.
- The Super key acts as the command center, with shortcuts for launching applications, managing windows, switching workspaces, and accessing system menus.
- Hyprland provides automatic tiling, animations, and a modern Wayland-based compositor.
- Quickshell ties together the status bar, theme switcher, notifications, and other interface elements into a cohesive layer.

## 🖥️ System requirements
- Omarchy targets x86_64 hardware and expects a relatively modern system.
- **Minimum requirements:**
  - 64-bit Intel or AMD processor (dual-core)
  - 4 GB of RAM
  - 10 GB of free disk space
  - SSD recommended for responsiveness
- **Recommended specs:**
  - Quad-core CPU (Intel Core i5, i7, or AMD Ryzen 5 and above)
  - 8 GB of RAM or more
  - 20 GB or more of free SSD storage
  - Modern GPU with up-to-date drivers

## 🎨 Graphics support
- Omarchy includes automated detection and installation of graphics drivers, including NVIDIA support optimized for Hyprland.
- AMD graphics are generally preferred for Wayland, but recent NVIDIA drivers work well on supported hardware.

## 🚀 Availability
- The recommended approach for most users is the official ISO.
- Existing Arch users can also transform their system with the installation script.

## 📥 Installation
- Download the latest Omarchy ISO from the official site.
- Create a bootable USB drive using a tool such as balenaEtcher or dd.
- Disable Secure Boot and TPM in your BIOS if necessary, then boot from the USB.
- The graphical installer guides you through partitioning, full-disk LUKS encryption setup, user creation, and package installation.
- The process typically completes within a few minutes on modern hardware.
- If you already run a clean Arch Linux installation, you can apply Omarchy on top of it.
  - The installer expects a vanilla Arch system with no conflicting desktop environments such as GNOME or KDE.
  - Run the installation script: `curl -fsSL https://omarchy.org/install | bash`
  - The script performs preflight checks, installs required packages, configures Hyprland, sets up Quickshell, applies themes, and enables system services.
  - Do not run the installer as root. It must be executed by a regular user on a supported Arch system.

## 🎯 Post-installation
- After installation, Omarchy boots directly into the Hyprland session.
- Press Super plus Space to open the app launcher.
- Press Super plus K to view the keybindings reference, which lists available shortcuts and their actions.

#Linux #ArchLinux #Hyprland #Omarchy #Wayland #DesktopEnvironment

---

*Source: [Omarchy: Install and Use the Opinionated Arch Linux Desktop - addROM](https://addrom.com/omarchy-install-and-use-the-opinionated-arch-linux-desktop/)*
