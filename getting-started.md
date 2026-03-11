---
title: Getting Started
layout: default
nav_order: 3
---
# Getting Started with z/TPF Extension

This guide will help you get up and running with the z/TPF VS Code Extension.

{: .no_toc }

## Table of Contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Quick Start

### Step 1: Install the Extension

If you haven't already, install the extension from the VS Code Marketplace. See the [Installation Guide](installation.md) for detailed instructions.

### Step 2: Connect to Your z/TPF System

1. Open the Command Palette (`Ctrl+Shift+P` / `Cmd+Shift+P`)
2. Type **"z/TPF: Connect to System"**
3. Enter your z/TPF system details:
   - Hostname or IP address
   - Port number
   - Username
   - Password (stored securely)

### Step 3: Open a z/TPF Workspace

1. Use **File > Open Folder** to open your local workspace
2. Or connect to a remote z/TPF directory:
   - Command Palette > **"z/TPF: Open Remote Folder"**
   - Navigate to your z/TPF project directory

---

## Your First z/TPF Project

### Creating a New File

1. In the Explorer view, right-click and select **New File**
2. Name your file with a z/TPF extension (e.g., `program.asm`)
3. The extension will automatically activate syntax highlighting

### Writing z/TPF Code

Start typing z/TPF assembly code. The extension provides:

```assembly
* Sample z/TPF Assembly Program
PROGRAM  CSECT
         USING *,R15
         
         L     R1,=A(MESSAGE)
         WTO   MF=(E,(1))
         
         BR    R14
         
MESSAGE  DC    C'Hello from z/TPF!'
         END   PROGRAM
```

**Features you'll notice:**
- Syntax highlighting for instructions and registers
- IntelliSense suggestions as you type
- Automatic indentation
- Error detection

---

## Basic Workflow

### 1. Edit Your Code

Use VS Code's powerful editing features:

- **Code Completion**: Press `Ctrl+Space` for suggestions
- **Go to Definition**: `F12` on any symbol
- **Find References**: `Shift+F12` to find all usages
- **Format Document**: `Shift+Alt+F` to auto-format

### 2. Build Your Program

To compile your z/TPF program:

1. Open the Command Palette (`Ctrl+Shift+P`)
2. Run **"z/TPF: Build Current File"**
3. View build output in the Terminal panel
4. Check for errors in the Problems panel

### 3. Debug Your Code

Set up debugging:

1. Click in the gutter to set breakpoints
2. Press `F5` to start debugging
3. Use the Debug toolbar to:
   - Continue (`F5`)
   - Step Over (`F10`)
   - Step Into (`F11`)
   - Step Out (`Shift+F11`)

### 4. Deploy to z/TPF

Deploy your compiled program:

1. Command Palette > **"z/TPF: Deploy to System"**
2. Select the target environment
3. Confirm deployment
4. Monitor the output for success

---

## Essential Commands

Access these commands via the Command Palette (`Ctrl+Shift+P` / `Cmd+Shift+P`):

| Command | Description |
|---------|-------------|
| `z/TPF: Connect to System` | Establish connection to z/TPF |
| `z/TPF: Disconnect` | Close z/TPF connection |
| `z/TPF: Build Current File` | Compile the active file |
| `z/TPF: Build All` | Compile all files in workspace |
| `z/TPF: Deploy to System` | Deploy compiled programs |
| `z/TPF: View System Logs` | Open z/TPF system logs |
| `z/TPF: Refresh File List` | Refresh remote file explorer |

---

## Keyboard Shortcuts

Default keyboard shortcuts:

| Shortcut | Action |
|----------|--------|
| `Ctrl+Shift+B` | Build current file |
| `F5` | Start debugging |
| `F9` | Toggle breakpoint |
| `F12` | Go to definition |
| `Shift+F12` | Find all references |
| `Ctrl+K Ctrl+D` | Format document |

Customize shortcuts in **File > Preferences > Keyboard Shortcuts**.

---

## Working with Remote Files

### Browse Remote Files

1. Open the z/TPF Explorer in the Activity Bar
2. Navigate through your remote directories
3. Click files to open them in the editor
4. Changes are automatically synced

### Upload/Download Files

**Upload local file:**
```
Right-click file > z/TPF: Upload to System
```

**Download remote file:**
```
Right-click in z/TPF Explorer > Download to Local
```

---

## Tips for Productivity

### Use Snippets

Type these prefixes and press `Tab`:

- `tpf-prog` - Create a basic program structure
- `tpf-macro` - Insert a macro definition
- `tpf-sub` - Create a subroutine template

### Customize Settings

Tailor the extension to your workflow:

1. Open Settings (`Ctrl+,`)
2. Search for "z/TPF"
3. Adjust preferences like:
   - Auto-save behavior
   - Build options
   - Syntax highlighting themes

### Use the Integrated Terminal

Access z/TPF commands directly:

1. Open Terminal (`Ctrl+` `)
2. Run z/TPF CLI commands
3. View real-time output

---

## Common Tasks

### Task 1: Create and Build a Program

```bash
1. Create new file: program.asm
2. Write your z/TPF code
3. Save the file (Ctrl+S)
4. Build: Ctrl+Shift+B
5. Check Problems panel for errors
```

### Task 2: Debug a Program

```bash
1. Set breakpoints (click gutter or F9)
2. Start debugging (F5)
3. Inspect variables in Debug panel
4. Step through code (F10/F11)
5. View call stack and locals
```

### Task 3: Deploy to Production

```bash
1. Build all files successfully
2. Run: z/TPF: Deploy to System
3. Select production environment
4. Confirm deployment
5. Verify in system logs
```

---

## Next Steps

Now that you're familiar with the basics:

- Explore [Features](features.md) for advanced capabilities
- Review [Configuration](configuration.md) for customization options
- Check out example projects on [GitHub](https://github.com/JoshuaRichey/justthedocstemp)

---

## Getting Help

If you need assistance:

- Check the [FAQ section](features.md#faq)
- Search [GitHub Issues](https://github.com/JoshuaRichey/justthedocstemp/issues)
- Join the [community discussions](https://github.com/JoshuaRichey/justthedocstemp/discussions)