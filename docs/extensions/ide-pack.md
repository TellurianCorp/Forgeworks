# Extensions Strategy

The ForgeWorks IDE utilizes a curated extension strategy to ensure a consistent and secure development experience.

## `forgeworks-ide-pack`

The Phase 1 extension pack includes pinned versions of the following extensions, all sourced from **OpenVSX**:

| Category | Extensions Included | Purpose |
| :--- | :--- | :--- |
| **Languages** | `ms-vscode.cpptools`, `golang.go`, `ms-python.python`, `rust-lang.rust-analyzer` | Core language support for C++, Go, Python, and Rust. |
| **Code Quality** | `esbenp.prettier-vscode`, `dbaeumer.vscode-eslint` | Enforcing code style and linting standards. |
| **API/Schema** | `zxh404.vscode-proto3`, `bufbuild.vscode-buf`, `42crunch.vscode-openapi` | Support for Protocol Buffers, Buf, and OpenAPI specifications. |
| **DevOps/Docs** | `ms-azuretools.vscode-docker`, `redhat.vscode-yaml`, `yzhang.markdown-all-in-one`, `jebbs.plantuml` | Tools for Docker, YAML configuration, and documentation generation (Markdown, PlantUML). |

## Future Governance Extension

A dedicated **Governance extension** (`forgeworks-governance`) is planned for Phase 2. This extension will integrate corporate compliance and security checks directly into the IDE workflow:

*   **Accessibility:** Surface AA/AAA contrast checks.
*   **Security:** Integrate **SBOM generation (Syft)** and **vulnerability scanning (Grype/Trivy)** as IDE tasks.
