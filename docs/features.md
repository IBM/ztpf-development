---
title: Features
layout: default
nav_order: 4
---

# Features Overview
{: .no_toc }

Explore the features of the IBM z/TPF Development Visual Studio Code Extension.

## Table of Contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Customizable Pipeline

The extension setting `ztpf-development.commands.pipeline` allows you to customize the pipeline that is used to build and deploy your application. This setting is a list of Visual Studio Code commands that are executed in order. The pipeline is started when you run the `z/TPF: Run Pipeline` command from the command palette.

---

## z/TPF Commands

The commands that are part of the pipeline can also be individually run from the command palette. This is useful when you want to run a specific command without running the entire pipeline.

---

## Project Build Script Generation

If a `maketpf.cntl` file is found in the working directory, the control file will always be used to build the project. If no `maketpf.cntl` file is found, the extension will generate a build script `build.sh` in the working directory using any `PROJECT_BUILD_COMPILE` or `PROJECT_BUILD_LINK` values found in the `maketpf.cfg` project configuration file. If none of the above are found, the user will be prompted to input the parameters of the `maketpf` command.

The script generation can be replaced with a different Visual Studio Code command contribution or manually by creating a file named `build.sh` in the working directory. The script will be executed when the `z/TPF: Build Changes` command is run.

---

## Build Output Parsing

If the `z/TPF: Build Changes` command encounters a recognized compile or assembler error in the build output, an entry will be added to the Problems view. This allows you to quickly navigate to the error in the editor. These problem markers will persist until the next time the `z/TPF: Build Changes` command is run.

---

## Testing

The extension integrates the z/TPF Automated Testing Framework (ATF) into the Visual Studio Code testing framework. Including values for `PROJECT_TEST_NAMESPACE` or `PROJECT_TEST_PROGRAM` in the `maketpf.cfg` project configuration file triggers the test discovery process.

---

## Snippets

The extension provides a set of snippets that can be used to quickly insert common code patterns into a `maketpf.cfg` file. These snippets can be accessed from the auto-complete menu when editing a `maketpf.cfg` file.

---

## Tracing

The extension is integrated into the Visual Studio Code tracing framework. This allows you to change the tracing level specifically for the extension and view the trace output in the Output view. This can be helpful when debugging issues with the extension, so the development team will ask you to enable more detailed tracing and provide the trace output when trying to diagnose problems.
