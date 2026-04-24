# IBM z/TPF Development

IBM z/TPF Development is an extension for Visual Studio Code that provides a set of tools to assit with program development for IBM z/TPF.

## Issues

Any [issues](https://github.com/IBM/ztpf-development/issues) reported directly on this repository will be handled on a best-effort basis by the development team. Priority will be given to issues reported via opening a case through the [IBM Support](https://www.ibm.com/mysupport/s/createrecord/NewCase) channel.

## License

- The license for IBM z/TPF Development can be found in the [LICENSE file](https://github.com/IBM/ztpf-development/blob/main/product/LICENSE) in the product folder in this repository.
- The notices for IBM z/TPF Development can be found in the [NOTICES file](https://github.com/IBM/ztpf-development/blob/main/product/NOTICES) in the product folder in this repository.
- All other files managed in this repository are intended for the purpose of presenting the [product documentation web site](https://IBM.github.io/ztpf-development). The license for these files can be found in the [LICENSE file](https://github.com/IBM/ztpf-development/blob/main/LICENSE) in the root folder of this repository.

## Privacy

[IBM's General Privacy Statement](https://www.ibm.com/privacy) applies to this software.

No telemetry or usage data collection is currently performed by this extension. For details on how to [disable telemetry](https://code.visualstudio.com/docs/getstarted/telemetry#_disable-telemetry-reporting), see the Visual Studio Code documentation.

## Core Capabilities

### 1. Automated Development Pipeline

The extension provides a fully automated pipeline (`z/TPF: Run Pipeline`) that orchestrates the entire development workflow:

- **Pull Changes** - Synchronizes code from remote Git repositories to Linux on IBM Z
- **Generate Build Script** - Creates project-specific build scripts from configuration
- **Build Changes** - Compiles and links code on the remote system
- **Generate OLDR Loadset** - Prepares loadsets using `loadtpf`
- **Load and Activate** - Deploys loadsets via OLDR REST services
- **Run Automated Tests** - Executes tests through the Automated Test Framework

The pipeline is fully customizable through the `Commands: Pipeline` setting, allowing developers to add, remove, or reorder tasks.

### 2. Individual Development Commands

Each pipeline task can be executed independently:

| Command | Description |
|---------|-------------|
| `z/TPF: Run Pipeline` | Execute the complete configured pipeline |
| `z/TPF: Pull Changes` | Pull code from Git repositories to Linux on IBM Z system |
| `z/TPF: Build Changes` | Build code on Linux on IBM Z system |
| `z/TPF: Pull and Build Changes` | Combined pull and build operation |
| `z/TPF: Generate Project Build Script` | Create build.sh from configuration |
| `z/TPF: Generate and Transfer OLDR Loadset` | Prepare and transfer loadsets |
| `z/TPF: Load and Activate OLDR Loadset` | Deploy loadsets to z/TPF system |
| `z/TPF: Retrieve Build Output` | Download build artifacts to local workspace |
| `z/TPF: Clean Up Project Output` | Remove build artifacts from remote system |
| `z/TPF: Check Remote Build Environment Configuration` | Validate remote environment setup |

### 3. Integrated Testing Framework

- **Test Explorer Integration** - z/TPF automated tests appear in Visual Studio Code's native Testing view
- **Test Discovery** - Automatically retrieves tests from z/TPF host based on configuration
- **Test Execution** - Run individual tests, namespaces, or entire test suites
- **Test Refresh** - Manual and automatic test list updates
- **Configuration-Driven** - Tests defined via `PROJECT_TEST_NAMESPACE` and `PROJECT_TEST_PROGRAM` variables

### 4. Build System Intelligence

The extension automatically discovers and uses the appropriate build method:

1. **bldtpf** - When `maketpf.cntl` control file exists
2. **Custom build.sh** - When project build script is present
3. **maketpf** - Fallback with user-provided parameters

Similar intelligence for loadtpf command discovery:
- Uses `maketpf.loaddeck` if available
- Falls back to `maketpf.cntl` with optional `maketpf.loadfile`
- Generates control file from `PROJECT_BUILD_LINK` configuration
- Prompts user for parameters as last resort

### 5. Remote System Integration

**SSH2-Based Communication:**
- Secure SSH key-based authentication
- SFTP file transfer capabilities
- Remote command execution
- Persistent connection management during pipeline execution

**Configuration Requirements:**
- Linux on IBM Z host and credentials
- SSH private key authentication

### 6. OLDR REST Service Integration

- HTTPS/HTTP communication with z/TPF OLDR services
- Loadset deployment and activation
- Configurable via `LOADTPF_HTTP_PORT` in project configuration

### 7. Language Support

**Custom Language Definitions:**
- **ztpf-config** - Configuration files (`maketpf.cfg`)
- **ztpf-loadfile** - Load files (`maketpf.loadfile`)
- **ztpf-control** - Control files (`maketpf.cntl`)
- **ztpf-loaddeck** - Loader input files (`maketpf.loaddeck`)

**Features:**
- Syntax highlighting (Makefile-based grammar)
- Code snippets for configuration files
- Automatic line ending normalization (LF)

### 8. Build Output Management

**Retrieve Build Output Command:**
- Searches `TPF_ROOT` and `APPL_ROOT` directories
- Pattern-based file filtering (default: `*.lst`)
- Preserves remote directory structure locally
- Automatic local directory creation
- Configurable output directory (default: `out`)
