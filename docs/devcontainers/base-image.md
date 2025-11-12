# DevContainers

The ForgeWorks IDE is optimized for containerized development using DevContainers, ensuring a consistent and reproducible environment across all projects.

## Base Image Specification

The core of the containerized environment is the custom base image:

*   **Image Name:** `ghcr.io/telluriancorp/forgeworks/base:0.1`
*   **Included Tooling:**
    *   Version Control: `git`
    *   Networking: `curl`
    *   Build Tools: `make`, `cmake`
    *   Languages: **Python 3** (+ `uv`/`pipx`), **Go**, **Node LTS** (+ `pnpm`), **Rust** toolchain, **Java 21**
    *   API/Schema: `protobuf`, `buf`, `grpcurl`, OpenAPI generators
    *   Containerization: **Docker CLI** (with DIND feature)

## Example `devcontainer.json`

The standard configuration ensures the environment is fully initialized upon creation:

```jsonc
{
  "name": "Forgeworks Base",
  "image": "ghcr.io/telluriancorp/forgeworks/base:0.1",
  "features": { "ghcr.io/devcontainers/features/docker-in-docker:2": {} },
  "postCreateCommand": "tellurian bootstrap",
  "customizations": {
    "vscode": {
      "extensions": ["tellurian.forgeworks-ide-pack"],
      "settings": {
        "files.eol": "\n",
        "editor.formatOnSave": true,
        "terminal.integrated.defaultProfile.linux": "bash"
      }
    }
  },
  "forwardPorts": [3000, 5173, 8000, 8080]
}
```

The `postCreateCommand` automatically runs `tellurian bootstrap` to finalize the environment setup, including fetching secrets and pre-commit hooks.
