---
title: Features
layout: default
nav_order: 4
---

# Features Overview

Explore the comprehensive features of the z/TPF VS Code Extension.

{: .no_toc }

## Table of Contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Code Editing Features

### Syntax Highlighting

Full syntax highlighting support for z/TPF assembly language:

- **Instructions**: All z/TPF assembly instructions
- **Registers**: General purpose and special registers
- **Macros**: System and user-defined macros
- **Comments**: Single-line and block comments
- **Labels**: Program labels and symbols
- **Literals**: String and numeric literals

### IntelliSense & Code Completion

Smart code completion as you type:

- **Instruction Completion**: Suggests valid z/TPF instructions
- **Register Completion**: Auto-completes register names
- **Macro Expansion**: Suggests available macros
- **Parameter Help**: Shows parameter information for instructions
- **Context-Aware**: Suggestions based on current context

### Code Navigation

Navigate your codebase efficiently:

- **Go to Definition** (`F12`): Jump to symbol definitions
- **Find All References** (`Shift+F12`): Locate all symbol usages
- **Go to Symbol** (`Ctrl+Shift+O`): Quick navigation within file
- **Peek Definition** (`Alt+F12`): View definition inline
- **Breadcrumbs**: Navigate file structure at the top

### Code Formatting

Automatic code formatting:

- **Format Document** (`Shift+Alt+F`): Format entire file
- **Format Selection**: Format selected code
- **Auto-indent**: Automatic indentation on new lines
- **Customizable Rules**: Configure formatting preferences

---

## Build & Compilation

### Integrated Build System

Compile z/TPF programs directly in VS Code:

- **Build Current File**: Compile the active file
- **Build All**: Compile all files in workspace
- **Incremental Builds**: Only rebuild changed files
- **Build Configurations**: Debug, Release, and custom configs
- **Build Output**: View compilation results in Terminal

### Error Detection

Real-time error detection and reporting:

- **Syntax Errors**: Highlighted in the editor
- **Semantic Errors**: Detected during compilation
- **Problems Panel**: Centralized error list
- **Quick Fixes**: Suggested fixes for common errors
- **Error Navigation**: Jump between errors quickly

### Build Tasks

Customizable build tasks:

```json
{
  "version": "2.0.0",
  "tasks": [
    {
      "label": "Build z/TPF Program",
      "type": "shell",
      "command": "ztpf-build",
      "group": {
        "kind": "build",
        "isDefault": true
      }
    }
  ]
}
```

---

## Debugging Features

### Interactive Debugging

Full debugging support for z/TPF applications:

- **Breakpoints**: Set, disable, and manage breakpoints
- **Step Execution**: Step over, into, and out of code
- **Variable Inspection**: View and modify variable values
- **Watch Expressions**: Monitor specific expressions
- **Call Stack**: Navigate the execution stack
- **Debug Console**: Execute commands during debugging

### Debug Configurations

Configure debugging sessions:

```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Debug z/TPF Program",
      "type": "ztpf",
      "request": "launch",
      "program": "${file}",
      "stopOnEntry": true
    }
  ]
}
```

### Advanced Debug Features

- **Conditional Breakpoints**: Break on specific conditions
- **Logpoints**: Log messages without stopping execution
- **Data Breakpoints**: Break on data changes
- **Exception Breakpoints**: Break on exceptions
- **Multi-session Debugging**: Debug multiple programs simultaneously

---

## Remote Development

### Remote File System

Work with files on remote z/TPF systems:

- **Browse Remote Files**: Navigate remote directories
- **Edit Remote Files**: Direct editing with auto-sync
- **Upload/Download**: Transfer files between local and remote
- **File Watching**: Auto-refresh on remote changes
- **Conflict Resolution**: Handle concurrent modifications

### Remote Execution

Execute commands on remote systems:

- **Remote Terminal**: SSH terminal integration
- **Command Execution**: Run z/TPF commands remotely
- **Output Streaming**: Real-time command output
- **Job Submission**: Submit and monitor batch jobs
- **Log Viewing**: Access system and application logs

### Connection Management

Manage multiple z/TPF connections:

- **Connection Profiles**: Save multiple system configurations
- **Quick Connect**: Switch between systems easily
- **Secure Storage**: Encrypted credential storage
- **Connection Status**: Visual connection indicators
- **Auto-reconnect**: Automatic reconnection on disconnect

---

## Code Snippets

### Built-in Snippets

Pre-defined code templates:

**Program Structure:**
```assembly
* Type: tpf-prog
PROGRAM  CSECT
         USING *,R15
         
         * Your code here
         
         BR    R14
         END   PROGRAM
```

**Macro Definition:**
```assembly
* Type: tpf-macro
&NAME    MACRO
&LABEL   &NAME &PARM1,&PARM2
         * Macro body
         MEND
```

**Subroutine:**
```assembly
* Type: tpf-sub
SUBR     DS    0H
         STM   R14,R12,12(R13)
         
         * Subroutine code
         
         LM    R14,R12,12(R13)
         BR    R14
```

### Custom Snippets

Create your own snippets:

1. Open Command Palette
2. Select **"Preferences: Configure User Snippets"**
3. Choose **"ztpf"**
4. Add your custom snippets

---

## Source Control Integration

### Git Integration

Full Git support for z/TPF projects:

- **Source Control View**: Manage changes visually
- **Commit**: Stage and commit changes
- **Branch Management**: Create, switch, and merge branches
- **Diff Viewer**: Compare file versions
- **History**: View commit history
- **Conflict Resolution**: Resolve merge conflicts

### Remote Repository Support

Work with remote repositories:

- **Push/Pull**: Sync with remote repositories
- **Clone**: Clone z/TPF projects
- **Pull Requests**: Create and review PRs
- **GitHub Integration**: Direct GitHub integration
- **GitLab Support**: GitLab repository support

---

## Productivity Tools

### Code Lens

Inline code information:

- **Reference Count**: Shows number of references
- **Implementation Count**: Shows implementations
- **Quick Actions**: Inline action buttons
- **Test Status**: Unit test results

### Refactoring

Code refactoring tools:

- **Rename Symbol** (`F2`): Rename across all files
- **Extract Method**: Extract code to subroutine
- **Inline Variable**: Inline variable usage
- **Move Symbol**: Move to different file

### Code Actions

Quick fixes and improvements:

- **Auto-import**: Automatically add missing imports
- **Generate Code**: Generate boilerplate code
- **Optimize**: Suggest optimizations
- **Convert**: Convert between formats

---

## Extension Settings

### Customization Options

Configure the extension to your needs:

```json
{
  "ztpf.connection.host": "your-ztpf-host",
  "ztpf.connection.port": 22,
  "ztpf.build.autoSave": true,
  "ztpf.editor.formatOnSave": true,
  "ztpf.debug.stopOnEntry": false,
  "ztpf.syntax.highlightStyle": "modern"
}
```

See the [Configuration Guide](configuration.md) for all available settings.

---

## Command Palette Commands

Access all features via Command Palette (`Ctrl+Shift+P`):

### Connection Commands
- `z/TPF: Connect to System`
- `z/TPF: Disconnect`
- `z/TPF: Switch Connection Profile`
- `z/TPF: Edit Connection Settings`

### Build Commands
- `z/TPF: Build Current File`
- `z/TPF: Build All`
- `z/TPF: Clean Build`
- `z/TPF: Rebuild All`

### Debug Commands
- `z/TPF: Start Debugging`
- `z/TPF: Stop Debugging`
- `z/TPF: Restart Debugging`
- `z/TPF: Toggle Breakpoint`

### File Commands
- `z/TPF: Open Remote File`
- `z/TPF: Upload File`
- `z/TPF: Download File`
- `z/TPF: Sync Workspace`

### Utility Commands
- `z/TPF: View System Logs`
- `z/TPF: Show Output Channel`
- `z/TPF: Clear Cache`
- `z/TPF: Report Issue`

---

## FAQ

### General Questions

**Q: What versions of z/TPF are supported?**  
A: The extension supports z/TPF 1.1 and later versions.

**Q: Can I use this extension offline?**  
A: Yes, for local files. Remote features require network connectivity.

**Q: Is my connection secure?**  
A: Yes, all connections use SSH with encrypted credentials.

### Troubleshooting

**Q: Why isn't syntax highlighting working?**  
A: Ensure your file has a recognized z/TPF extension (.asm, .mac, etc.).

**Q: Build fails with connection error?**  
A: Check your connection settings and network connectivity.

**Q: How do I report a bug?**  
A: Use the [GitHub Issues](https://github.com/JoshuaRichey/justthedocstemp/issues) page.

---

## Performance Tips

### Optimize Your Workflow

- **Use Workspaces**: Organize related projects
- **Enable Auto-save**: Reduce manual saves
- **Configure Exclusions**: Exclude unnecessary files
- **Use Remote Caching**: Cache remote files locally
- **Limit Extensions**: Disable unused extensions

### Large Projects

For large z/TPF projects:

- Use **File Watchers** selectively
- Enable **Lazy Loading** for remote files
- Configure **Build Parallelization**
- Use **Incremental Builds**
- Optimize **Search Scope**

---

## What's New

### Recent Updates

Check the [Changelog](https://github.com/JoshuaRichey/justthedocstemp/blob/main/CHANGELOG.md) for the latest features and improvements.

### Upcoming Features

- Enhanced macro expansion
- Improved debugging capabilities
- Additional code refactoring tools
- Performance optimizations
- Extended language support

---

## Feedback & Contributions

We welcome your feedback and contributions:

- **Feature Requests**: [GitHub Issues](https://github.com/JoshuaRichey/justthedocstemp/issues)
- **Bug Reports**: [GitHub Issues](https://github.com/JoshuaRichey/justthedocstemp/issues)
- **Discussions**: [GitHub Discussions](https://github.com/JoshuaRichey/justthedocstemp/discussions)
- **Contributions**: [Contributing Guide](https://github.com/JoshuaRichey/justthedocstemp/blob/main/CONTRIBUTING.md)