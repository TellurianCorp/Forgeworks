# Introduction to Tellurian ForgeWorks IDE

The **Tellurian ForgeWorks IDE** is a customized, enterprise-grade development environment built upon the open-source **VSCodium** platform. Its primary goal is to provide Tellurian Corp engineers with a standardized, secure, and pre-configured toolchain for all internal development projects.

## 1. Scope and Goals (Phase 1)

The initial phase (Months 1–2) focuses on establishing the foundational elements of the IDE:

*   **Platform:** Forking VSCodium and injecting Tellurian branding and policies.
*   **Distribution:** Building signed, cross-platform installers for Windows, macOS (Intel/ARM), and Linux (AppImage/Deb/RPM).
*   **Tooling:** Publishing the curated `forgeworks-ide-pack` extension list to OpenVSX.
*   **CLI:** Shipping the minimal `tellurian` CLI with `login`, `bootstrap`, and `run dev` subcommands.
*   **DevContainers:** Creating the initial `devcontainers/base` image and a language profile (Go or Python).

## 2. Branding and Customization

The IDE is heavily branded to align with Tellurian Corp's identity. This includes:

| Branding Element | Value |
| :--- | :--- |
| **Short Name** | Forgeworks |
| **Long Name** | Tellurian Forgeworks |
| **Application Name** | forgeworks |
| **Data Folder** | `.forgeworks` (e.g., `~/.forgeworks`) |
| **Extension Gallery** | OpenVSX endpoints |
| **Assets** | Custom `logo.svg`, `icon.icns`, `icon.ico`, and `splash.png` |

## 3. Update Channels

The IDE supports two distinct update channels, managed via an internal update feed hosted on the Tellurian portal with signed manifests:

*   **Stable:** The default channel for all internal users, providing validated and stable releases.
*   **Insiders:** The channel for platform engineers and early adopters, providing access to the latest features and fixes.
