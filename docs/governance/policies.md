# Governance and Policies

The ForgeWorks IDE enforces several mandatory policies to ensure security, compliance, and code quality across all Tellurian Corp projects. These policies are injected into the IDE's configuration and cannot be overridden by the user.

## Enforced Policies (Locked Settings)

The following settings are locked via `core/policies/` to enforce corporate standards:

| Setting Key | Enforced Value | Rationale |
| :--- | :--- | :--- |
| `telemetry.telemetryLevel` | `"off"` | Ensures no usage data or telemetry is transmitted, adhering to internal privacy standards. |
| `security.workspace.trust.enabled` | `true` | Requires users to explicitly trust a workspace before code execution, mitigating supply chain risks. |
| `editor.formatOnSave` | `true` | Enforces consistent code formatting across the organization, improving readability and reducing merge conflicts. |
| `update.mode` | `"default"` | Directs the IDE to use the internal update channel for controlled and signed updates. |

## Licensing

The ForgeWorks IDE adheres to the following licensing structure:

*   **Core IDE:** Based on VSCodium, which is licensed under the MIT License.
*   **Tellurian Components:** All custom components, including the `tellurian` CLI and the governance extension, are licensed under the **TIL-1.0** (Tellurian Internal License 1.0).
*   **Documentation:** All documentation is licensed under the MIT License.
