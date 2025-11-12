# Phase 1 Technical Specification

This document details the technical requirements and implementation plan for the Foundation Phase (Phase 1) of the Tellurian ForgeWorks IDE.

## 1. Build and Packaging

The build process is designed for cross-platform compatibility and enterprise-grade security, including mandatory code signing.

### Build Prerequisites

| Platform | Required Tooling |
| :--- | :--- |
| **Windows** | Node.js LTS, Yarn/PNPM, Python 3, VS Build Tools, `signtool` access. |
| **macOS** | Xcode CLT, Node.js LTS, Yarn/PNPM, Python 3, Apple Developer ID for signing/notarization. |
| **Linux** | Node.js LTS, Yarn/PNPM, Python 3, system packaging deps (`rpm`, `debhelper`, `fuse`). |

### Packaging Outputs

All outputs are signed with the Tellurian Corp EV certificate (Windows/macOS) or package signing keys (Linux).

| Platform | Output Artifacts |
| :--- | :--- |
| **Windows** | `Forgeworks-Setup-x64.exe` |
| **macOS** | `Forgeworks-darwin-universal.dmg` |
| **Linux** | `Forgeworks.AppImage`, `.deb`, `.rpm` |

## 2. CI/CD Workflows

The Continuous Integration/Continuous Deployment is managed via GitHub Actions.

| Workflow | Purpose |
| :--- | :--- |
| `build-core.yml` | Builds per-platform artifacts, signs them, and uploads them to Releases. |
| `build-cli.yml` | Matrix build for the `tellurian` CLI (linux, windows, darwin; amd64/arm64). |
| `release.yml` | Creates draft releases, including checksums and **SBOMs (Software Bill of Materials)**. |
| `codeql.yml` | Performs static analysis across the `core/` and `cli/` repositories. |

### Security Requirements
*   Signing credentials must be stored in OIDC-gated secrets.
*   An SBOM and vulnerability scan (using Syft/Grype/Trivy) must be generated on every release.
*   Vulnerability reports (SARIF) must be attached to code scanning.
