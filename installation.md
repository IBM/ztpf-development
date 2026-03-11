---
title: Installation
layout: default
nav_order: 2
---

# Installation Guide

This guide will walk you through installing the z/TPF VS Code Extension.

{: .no_toc }

## Table of Contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Prerequisites

Before installing the extension, ensure you have:

- **Visual Studio Code** version 1.75.0 or higher
- **Network access** to your z/TPF development system
- **Valid credentials** for z/TPF system authentication

---

## Installation Methods

### Method 1: Install from VS Code Marketplace (Recommended)

1. Open Visual Studio Code
2. Click on the **Extensions** icon in the Activity Bar (or press `Ctrl+Shift+X` / `Cmd+Shift+X`)
3. Search for **"z/TPF"** in the search bar
4. Click **Install** on the z/TPF VS Code Extension
5. Reload VS Code when prompted

### Method 2: Install from VSIX File

If you have a `.vsix` file:

1. Open Visual Studio Code
2. Go to **Extensions** view (`Ctrl+Shift+X` / `Cmd+Shift+X`)
3. Click the **"..."** menu at the top of the Extensions view
4. Select **"Install from VSIX..."**
5. Navigate to and select the `.vsix` file
6. Reload VS Code when prompted

### Method 3: Install via Command Line

```bash
code --install-extension JoshuaRichey.ztpf-vscode
```

---

## Verify Installation

After installation, verify the extension is active:

1. Open the **Extensions** view
2. Search for "z/TPF" in the installed extensions
3. You should see the extension listed with a green checkmark
4. Check the status bar for z/TPF indicators

---

## Initial Configuration

After installation, you'll need to configure the extension:

1. Open VS Code Settings (`Ctrl+,` / `Cmd+,`)
2. Search for "z/TPF"
3. Configure the following settings:
   - **Host**: Your z/TPF system hostname or IP address
   - **Port**: Connection port (default: 22)
   - **Username**: Your z/TPF username
   - **Workspace Path**: Remote workspace directory

See the [Configuration Guide](configuration.md) for detailed setup instructions.

---

## Troubleshooting

### Extension Not Loading

If the extension doesn't load:

1. Check the **Output** panel (`View > Output`)
2. Select **"z/TPF Extension"** from the dropdown
3. Review any error messages
4. Ensure VS Code is up to date

### Connection Issues

If you can't connect to your z/TPF system:

1. Verify network connectivity to the host
2. Check firewall settings
3. Confirm credentials are correct
4. Review the [Configuration Guide](configuration.md)

### Getting Help

If you encounter issues:

- Check the [GitHub Issues](https://github.com/JoshuaRichey/justthedocstemp/issues) page
- Review existing issues or create a new one
- Include VS Code version, extension version, and error logs

---

## Updating the Extension

The extension will automatically check for updates. To manually update:

1. Open the **Extensions** view
2. Find the z/TPF extension
3. Click **Update** if available
4. Reload VS Code when prompted

---

## Uninstallation

To remove the extension:

1. Open the **Extensions** view
2. Find the z/TPF extension
3. Click the gear icon
4. Select **Uninstall**
5. Reload VS Code when prompted

---

## Next Steps

- [Getting Started Guide](getting-started.md) - Learn the basics
- [Configuration Guide](configuration.md) - Set up your environment
- [Features Overview](features.md) - Explore capabilities