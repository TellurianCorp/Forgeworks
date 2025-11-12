# CLI Reference: `tellurian`

The `tellurian` Command Line Interface is the primary tool for integrating the ForgeWorks IDE with the Tellurian Corp development ecosystem. It is recommended to be built in Go for static builds.

## Subcommands (Minimum Viable Product)

| Subcommand | Description |
| :--- | :--- |
| `tellurian login` | Initiates the OIDC device flow for authentication against the internal **NovaTellus auth** system. This is required to access internal resources and secrets. |
| `tellurian bootstrap` | **Project Setup:** Executes environment setup tasks, including installing pre-commit hooks, fetching secrets, hydrating `.env.local` files, and pre-pulling necessary DevContainer images. |
| `tellurian run dev` | **Local Development:** A language-aware runner that starts the current project's service (e.g., a FastAPI or Go service) with hot-reload functionality enabled. |

## Configuration and Secrets

*   **Configuration File:** `~/.config/forgeworks/config.yaml` stores non-sensitive configuration such as tokens, organization details, and registry endpoints.
*   **Secrets Management:** Secrets required for project setup and execution are fetched from a configured vault, such as **1Password** or **Azure Key Vault**.
