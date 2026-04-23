---
title: Configuration
layout: default
nav_order: 5
---

# Configuration Guide

Learn how to configure the z/TPF VS Code Extension to match your development environment and preferences.

{: .no_toc }

## Table of Contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Accessing Settings

### Via VS Code Settings UI

1. Open Settings: `Ctrl+,` (Windows/Linux) or `Cmd+,` (macOS)
2. Search for **"z/TPF"**
3. Modify settings using the UI

### Via settings.json

1. Open Command Palette: `Ctrl+Shift+P` / `Cmd+Shift+P`
2. Type **"Preferences: Open Settings (JSON)"**
3. Add z/TPF configuration:

```json
{
  "ztpf.connection.host": "your-host.example.com",
  "ztpf.connection.port": 22,
  "ztpf.connection.username": "your-username"
}
```

---

## Connection Settings

### Basic Connection

Configure your z/TPF system connection:

```json
{
  "ztpf.connection.host": "ztpf-dev.example.com",
  "ztpf.connection.port": 22,
  "ztpf.connection.username": "developer",
  "ztpf.connection.timeout": 30000,
  "ztpf.connection.keepAlive": true
}
```

| Setting | Type | Default | Description |
|---------|------|---------|-------------|
| `host` | string | `""` | z/TPF system hostname or IP |
| `port` | number | `22` | SSH connection port |
| `username` | string | `""` | Your z/TPF username |
| `timeout` | number | `30000` | Connection timeout (ms) |
| `keepAlive` | boolean | `true` | Keep connection alive |

### Authentication

Configure authentication methods:

```json
{
  "ztpf.connection.authMethod": "password",
  "ztpf.connection.privateKeyPath": "~/.ssh/id_rsa",
  "ztpf.connection.passphrase": "",
  "ztpf.connection.savePassword": false
}
```

**Authentication Methods:**
- `password` - Username/password authentication
- `publickey` - SSH key authentication
- `keyboard-interactive` - Interactive authentication

{: .warning }
> **Security Note**: Passwords are stored securely in VS Code's credential store. Never commit passwords to version control.

### Connection Profiles

Create multiple connection profiles:

```json
{
  "ztpf.connection.profiles": [
    {
      "name": "Development",
      "host": "ztpf-dev.example.com",
      "port": 22,
      "username": "dev-user"
    },
    {
      "name": "Testing",
      "host": "ztpf-test.example.com",
      "port": 22,
      "username": "test-user"
    },
    {
      "name": "Production",
      "host": "ztpf-prod.example.com",
      "port": 22,
      "username": "prod-user"
    }
  ],
  "ztpf.connection.activeProfile": "Development"
}
```

---

## Editor Settings

### Syntax Highlighting

Customize syntax highlighting:

```json
{
  "ztpf.editor.syntax.enabled": true,
  "ztpf.editor.syntax.theme": "modern",
  "ztpf.editor.syntax.highlightRegisters": true,
  "ztpf.editor.syntax.highlightMacros": true,
  "ztpf.editor.syntax.highlightComments": true
}
```

### Code Formatting

Configure automatic formatting:

```json
{
  "ztpf.editor.formatOnSave": true,
  "ztpf.editor.formatOnType": false,
  "ztpf.editor.tabSize": 8,
  "ztpf.editor.insertSpaces": false,
  "ztpf.editor.trimTrailingWhitespace": true,
  "ztpf.editor.indentStyle": "classic"
}
```

**Indent Styles:**
- `classic` - Traditional z/TPF indentation
- `modern` - Modern structured indentation
- `custom` - Use custom rules

### IntelliSense

Configure code completion:

```json
{
  "ztpf.intellisense.enabled": true,
  "ztpf.intellisense.suggestInstructions": true,
  "ztpf.intellisense.suggestRegisters": true,
  "ztpf.intellisense.suggestMacros": true,
  "ztpf.intellisense.triggerCharacters": [".", ",", " "],
  "ztpf.intellisense.maxSuggestions": 50
}
```

---

## Build Settings

### Build Configuration

Configure build behavior:

```json
{
  "ztpf.build.autoSave": true,
  "ztpf.build.showOutput": true,
  "ztpf.build.clearOutputOnBuild": true,
  "ztpf.build.stopOnError": true,
  "ztpf.build.parallelBuilds": 4
}
```

### Build Options

Set compiler options:

```json
{
  "ztpf.build.compiler": "ztpf-asm",
  "ztpf.build.compilerArgs": [
    "-O2",
    "-Wall",
    "-Werror"
  ],
  "ztpf.build.outputDirectory": "./build",
  "ztpf.build.intermediateDirectory": "./obj"
}
```

### Build Configurations

Define multiple build configurations:

```json
{
  "ztpf.build.configurations": {
    "Debug": {
      "compilerArgs": ["-g", "-O0"],
      "defines": ["DEBUG=1"]
    },
    "Release": {
      "compilerArgs": ["-O3"],
      "defines": ["NDEBUG=1"]
    },
    "Test": {
      "compilerArgs": ["-g", "-O1"],
      "defines": ["TEST=1", "DEBUG=1"]
    }
  },
  "ztpf.build.activeConfiguration": "Debug"
}
```

---

## Debug Settings

### Debug Configuration

Configure debugging behavior:

```json
{
  "ztpf.debug.stopOnEntry": false,
  "ztpf.debug.showDisassembly": false,
  "ztpf.debug.showRegisters": true,
  "ztpf.debug.showMemory": true,
  "ztpf.debug.maxStackDepth": 50
}
```

### Breakpoint Settings

Configure breakpoint behavior:

```json
{
  "ztpf.debug.breakpoints.enabled": true,
  "ztpf.debug.breakpoints.validateOnStart": true,
  "ztpf.debug.breakpoints.showInGutter": true,
  "ztpf.debug.breakpoints.allowConditional": true
}
```

### Debug Output

Configure debug output:

```json
{
  "ztpf.debug.output.showConsole": true,
  "ztpf.debug.output.showVariables": true,
  "ztpf.debug.output.showCallStack": true,
  "ztpf.debug.output.verbosity": "normal"
}
```

**Verbosity Levels:**
- `minimal` - Essential information only
- `normal` - Standard debug output
- `verbose` - Detailed debug information
- `trace` - All debug events

---

## Remote File Settings

### File Synchronization

Configure file sync behavior:

```json
{
  "ztpf.remote.autoSync": true,
  "ztpf.remote.syncOnSave": true,
  "ztpf.remote.syncInterval": 5000,
  "ztpf.remote.conflictResolution": "prompt"
}
```

**Conflict Resolution:**
- `prompt` - Ask user what to do
- `local` - Prefer local changes
- `remote` - Prefer remote changes
- `newest` - Use newest version

### File Watching

Configure file watching:

```json
{
  "ztpf.remote.watchFiles": true,
  "ztpf.remote.watchInterval": 2000,
  "ztpf.remote.watchExclude": [
    "**/.git/**",
    "**/node_modules/**",
    "**/build/**"
  ]
}
```

### File Transfer

Configure file transfer settings:

```json
{
  "ztpf.remote.transfer.compression": true,
  "ztpf.remote.transfer.maxFileSize": 10485760,
  "ztpf.remote.transfer.timeout": 60000,
  "ztpf.remote.transfer.retries": 3
}
```

---

## Performance Settings

### Caching

Configure caching behavior:

```json
{
  "ztpf.performance.cache.enabled": true,
  "ztpf.performance.cache.maxSize": 104857600,
  "ztpf.performance.cache.ttl": 3600000,
  "ztpf.performance.cache.clearOnDisconnect": false
}
```

### Resource Limits

Set resource limits:

```json
{
  "ztpf.performance.maxConcurrentConnections": 5,
  "ztpf.performance.maxFileSize": 10485760,
  "ztpf.performance.maxSearchResults": 1000,
  "ztpf.performance.lazyLoadThreshold": 100
}
```

---

## Logging & Diagnostics

### Logging Configuration

Configure logging:

```json
{
  "ztpf.logging.enabled": true,
  "ztpf.logging.level": "info",
  "ztpf.logging.outputChannel": true,
  "ztpf.logging.file": "",
  "ztpf.logging.maxFileSize": 10485760
}
```

**Log Levels:**
- `error` - Errors only
- `warn` - Warnings and errors
- `info` - Informational messages
- `debug` - Debug information
- `trace` - Detailed trace logs

### Diagnostics

Enable diagnostic features:

```json
{
  "ztpf.diagnostics.enabled": true,
  "ztpf.diagnostics.showInProblems": true,
  "ztpf.diagnostics.validateOnType": false,
  "ztpf.diagnostics.validateOnSave": true,
  "ztpf.diagnostics.maxProblems": 100
}
```

---

## Workspace Settings

### Workspace Configuration

Configure workspace-specific settings in `.vscode/settings.json`:

```json
{
  "ztpf.workspace.root": "${workspaceFolder}",
  "ztpf.workspace.sourceDirectory": "src",
  "ztpf.workspace.buildDirectory": "build",
  "ztpf.workspace.includeDirectories": [
    "include",
    "macros"
  ]
}
```

### Project Files

Configure project file handling:

```json
{
  "ztpf.project.configFile": ".ztpfrc",
  "ztpf.project.autoDetect": true,
  "ztpf.project.fileExtensions": [
    ".asm",
    ".mac",
    ".inc",
    ".tpf"
  ]
}
```

---

## Advanced Settings

### Experimental Features

Enable experimental features:

```json
{
  "ztpf.experimental.enableNewParser": false,
  "ztpf.experimental.enableAIAssist": false,
  "ztpf.experimental.enableAdvancedRefactoring": false
}
```

{: .warning }
> **Warning**: Experimental features may be unstable. Use with caution in production environments.

### Custom Commands

Define custom commands:

```json
{
  "ztpf.customCommands": [
    {
      "name": "Deploy to Dev",
      "command": "deploy-dev.sh",
      "args": ["${file}"]
    },
    {
      "name": "Run Tests",
      "command": "run-tests.sh",
      "args": ["${workspaceFolder}"]
    }
  ]
}
```

---

## Configuration Examples

### Minimal Configuration

Basic setup for getting started:

```json
{
  "ztpf.connection.host": "ztpf-dev.example.com",
  "ztpf.connection.username": "developer",
  "ztpf.editor.formatOnSave": true
}
```

### Development Configuration

Optimized for development:

```json
{
  "ztpf.connection.host": "ztpf-dev.example.com",
  "ztpf.connection.username": "developer",
  "ztpf.editor.formatOnSave": true,
  "ztpf.build.autoSave": true,
  "ztpf.build.activeConfiguration": "Debug",
  "ztpf.debug.stopOnEntry": false,
  "ztpf.remote.autoSync": true,
  "ztpf.logging.level": "debug"
}
```

### Production Configuration

Optimized for production work:

```json
{
  "ztpf.connection.host": "ztpf-prod.example.com",
  "ztpf.connection.username": "prod-user",
  "ztpf.editor.formatOnSave": true,
  "ztpf.build.stopOnError": true,
  "ztpf.build.activeConfiguration": "Release",
  "ztpf.remote.conflictResolution": "prompt",
  "ztpf.logging.level": "warn"
}
```

---

## Environment Variables

The extension supports these environment variables:

| Variable | Description |
|----------|-------------|
| `ZTPF_HOST` | Override connection host |
| `ZTPF_PORT` | Override connection port |
| `ZTPF_USER` | Override username |
| `ZTPF_HOME` | z/TPF home directory |
| `ZTPF_CONFIG` | Path to config file |

Set in your shell or `.env` file:

```bash
export ZTPF_HOST=ztpf-dev.example.com
export ZTPF_USER=developer
export ZTPF_HOME=/home/developer/ztpf
```

---

## Troubleshooting Configuration

### Reset to Defaults

To reset all settings to defaults:

1. Open Command Palette
2. Run **"z/TPF: Reset Configuration"**
3. Confirm the reset

### Validate Configuration

Check your configuration:

1. Open Command Palette
2. Run **"z/TPF: Validate Configuration"**
3. Review any warnings or errors

### Export/Import Settings

**Export settings:**
```
Command Palette > z/TPF: Export Settings
```

**Import settings:**
```
Command Palette > z/TPF: Import Settings
```

---

## Next Steps

- Review [Features](features.md) to explore capabilities
- Check [Getting Started](getting-started.md) for usage examples
- Visit [GitHub](https://github.com/JoshuaRichey/justthedocstemp) for more resources