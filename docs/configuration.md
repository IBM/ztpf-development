---
title: Configuration
layout: default
nav_order: 5
---

# Configuration Guide
{: .no_toc }

Learn how to configure the settings for the IBM z/TPF Development Visual Studio Code extension.
Learn how to configure the project using the `maketpf` project configuration files.

## Table of Contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Accessing Extension Settings

### Via Visual Studio Code Settings UI

1. Open Settings: `Ctrl+,` (Windows/Linux) or `Cmd+,` (macOS)
2. Search for **"IBM z/TPF Development"**
3. Modify settings using the UI

### Via settings.json

1. Open Command Palette: `Ctrl+Shift+P` / `Cmd+Shift+P`
2. Type **"Preferences: Open Settings (JSON)"**
3. Add IBM z/TPF Development configuration:

```json
{
  "ztpf-development.linux.base": "/path/to/folder",
  "ztpf-development.linux.host": "example.org",
  "ztpf-development.linux.port": 22
}
```

---

## Required Extension Settings

The following settings must be set by the user in order to use the IBM z/TPF Development Visual Studio Code Extension:

- `ztpf-development.linux.base` - The user's workspace directory on the Linux on IBM Z system
- `ztpf-development.linux.host` - The hostname or IP address of the Linux on IBM Z system
- `ztpf-development.linux.userId` - The username for the SSH connection to the Linux on IBM Z system
- `ztpf-development.linux.privateKey` - Local file path for the SSH private key file for the SSH connection to the Linux on IBM Z system

Check the default values for any additional `ztpf-development` settings not listed here for completeness: for example, the SSH server port on the Linux on IBM Z system may not be the default value of `22`.

---

## Project Configuration

A `maketpf.cfg` file instructs the build tools on Linux on IBM Z how to build the project. See the manpages for `maketpf.cfg` for the complete overview of the options available.

The extension includes new configuration options to the `maketpf.cfg` file to perform particular tasks:
- `PROJECT_BUILD_COMPILE`: the name of a source file to pass to `maketpf -f <value>` in order to compile or assemble
- `PROJECT_BUILD_LINK`: the name of a program to pass to `maketpf <value> link` in order to link the shared object
- `PROJECT_TEST_NAMESPACE`: the name of a z/TPF Automated Test Framework namespace used to discover and run tests
- `PROJECT_TEST_PROGRAM`: the name of a program that contains z/TPF Automated Test Framework tests
- `LOADTPF_HTTP_PORT`: the HTTPS/HTTP port to use for making REST service requests

---

## Next Steps

- Review [Features](features.html) to explore capabilities
- Check [Getting Started](getting-started.html) for usage examples
