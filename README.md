https://codespaces.new/scmlab/gcl-sample-container?quickstart=1

# gcl-sample-container

Sample GCL programs for the [GCL VS Code extension](https://marketplace.visualstudio.com/items?itemName=scmlab.gcl-vscode), version **0.0.4**.

Use this repository in GitHub Codespaces or in a local VS Code Dev Container with Docker.

The Dev Container uses Microsoft's Ubuntu 26.04 base image and installs `scmlab.gcl-vscode@0.0.4` from the Marketplace inside the container. The platform-specific extension includes the `gcl` language server and Z3. No separate installation of GCL, Z3, or Haskell is needed.

## Run locally with VS Code and Docker

Install:

- [Visual Studio Code](https://code.visualstudio.com/), version 1.85 or later.
- [Docker](https://www.docker.com/) and make sure it is running.
- The [Dev Containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) for VS Code.
- [Git](https://git-scm.com/).

Clone and open this repository:

```sh
git clone https://github.com/scmlab/gcl-sample-container.git
code gcl-sample-container
```

1. Choose **Reopen in Container** when prompted. You can also run **Dev Containers: Reopen in Container** from the Command Palette.
2. Wait for the container setup and extension installation to finish. The first launch requires an internet connection to download the image and extension.
3. Open `increment.gcl`.
4. Run **GCL: Reload** from the Command Palette to see its proof obligations and results. The simple assignment should be proved successfully (`Q.E.D.`).

On macOS and Windows, the container still runs Linux. VS Code selects the Linux x64 or ARM64 extension to match the container's architecture.

## Run in GitHub Codespaces

On this repository's GitHub page, choose **Code → Codespaces → Create codespace on main**. A GitHub account with available Codespaces usage is required; Docker is not needed on your computer.

Wait for setup to finish, then open `increment.gcl` and run **GCL: Reload**. Codespaces uses the same Dev Container configuration as local VS Code.

## Examples

- `increment.gcl`: a small assignment with a precondition and postcondition. Use this first to check that the environment works.
- `gcd.gcl`: Euclid's algorithm with a loop invariant and bound. It declares `gcd` as a function without defining its properties, so some proof obligations are reported as `Falsifiable`. This example is not expected to prove every obligation successfully as written.

## Extension version

The extension version is specified in `.devcontainer/devcontainer.json`. The bundled language server and Z3 come from that extension package.

The `publisher.extension@version` syntax installs a specific version. VS Code supports [pinning versions against automatic updates](https://code.visualstudio.com/updates/v1_75#_pin-an-extension-version-from-cli). For this course, keep GCL at **0.0.4** and leave automatic updates disabled for this extension. You can check the installed version and its **Auto Update** option on the extension's details page inside the container.

If the container image or extension version is changed in the configuration, run **Dev Containers: Rebuild Container** locally or **Codespaces: Rebuild Container** in Codespaces to apply it.
