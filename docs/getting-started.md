---
title: Getting Started
layout: default
nav_order: 3
---

# Getting Started with IBM z/TPF Development Extension
{: .no_toc }

This guide will help you get up and running with the IBM z/TPF Development Visual Studio Code Extension.

This guide assumes that:

- GitHub is being used for the source control system
- That the default pipeline tasks are being used.

If you are using a different source control system or different pipeline commands, you will need to adjust the instructions accordingly.

## Table of Contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Quick Start

### Step 1: Install the Extension

If you haven't already, install the extension from the Visual Studio Code Marketplace. See the [Installation Guide](installation.html) for detailed instructions.

### Step 2: Setup Credentials

Workstation -> GitHub - create a public-private SSH key pair and add the public key to your GitHub account.
Workstation -> Linux on IBM Z - create a public-private SSH key pair and add the public key to your Linux on IBM Z account.
Linux on IBM Z -> GitHub - create a public-private SSH key pair and add the public key to your GitHub account.

### Step 3: Setup the Workspaces

Because development for z/TPF programs is done on a remote Linux on IBM Z system and can require multiple Git repositories, the workspace layout is different from most software development projects.

The recommended layout for your local workspace is:

- create a new local directory that is the root of your workspace
- In the workspace root, create a `build` directory. This is where the project configuration files (`maketpf.cfg`, `maketpf.cntl`, `maketpf.loadfile` and `maketpf.loaddeck`) are stored.
- In the workspace root, clone any Git repositories that contain the z/TPF program source code.

The recommended layout for your remote workspace is to closely mirror the local workspace layout:

- create a new remote directory that is the root of your workspace
- In the workspace root, create a `build` directory. This is where the project configuration files (`maketpf.cfg`, `maketpf.cntl`, `maketpf.loadfile` and `maketpf.loaddeck`) are stored and where any remote commands will be run.
- In the workspace root, clone any Git repositories that contain the z/TPF program source code.
  - The extension expects that the names of the remote clones match the names of the local clones e.g. (`myRepo` on the local machine and `myRepo` on the remote machine).
  - The number of remote clones should at least match the number of local clones. If there are more remote clones than local clones, the additional clones will be ignored.

### Step 4: Configure the Extension Settings

Review the [Configuration Guide](configuration.html) to configure the required extension settings.

### Step 5: Edit Your Code

Use the editing feature of Visual Studio Code and other extensions to make changes to the z/TPF program.

### Step 6: Commit Any Changes

Commit and push any changes to GitHub into your working branch.

### Step 7: Run the Development Pipeline

1. Open the Command Palette (`Ctrl+Shift+P`)
2. Run **"z/TPF: Run Pipeline"**
3. The pipeline will pull the latest changes to the remote workspace.
4. The pipeline will build the z/TPF program(s) in the remote workspace.
5. The pipeline will deploy a z/TPF loadset to the z/TPF system.
6. The pipeline will run a suite of z/TPF Automated Test Framework tests on the z/TPF system.

### Step 8: Review the results

Review the compile results in the **Problems** view.
Review the test results in the **Testing** view.

### Step 9: Iterate

Make additional changes to complete the project.

---

## Essential Commands

Access these commands via the Command Palette (`Ctrl+Shift+P` / `Cmd+Shift+P`):

| Command                                       | Description                          |
| --------------------------------------------- | ------------------------------------ |
| **z/TPF: Run Pipeline**                       | Run the development pipeline         |
| **z/TPF: Pull Changes**                       | Update Linux on IBM Z with Git       |
| **z/TPF: Build Changes**                      | Run build commands on Linux on IBM Z |
| **z/TPF: Generate and Transfer OLDR Loadset** | Run load commands on Linux on IBM Z  |
| **z/TPF: Load and Activate OLDR Loadset**     | OLDR Load and Activate on z/TPF      |

---

## Next Steps

Now that you're familiar with the basics:

- Explore [Features](features.html) for advanced capabilities
- Review [Configuration](configuration.html) for customization options
