# Reviewer Template (Legacy)

> [!WARNING]
> Keep this file only for compatibility with older deployments.

## Preferred replacement
Use these instead:
- `packs/core/critic/TEMPLATE.md`
- `packs/core/verifier/TEMPLATE.md`

## Legacy role summary
The old reviewer combined two jobs:
1. critique and gap finding
2. acceptance checking

That pattern is still usable for small systems, but it is weaker than separating critique from verification.

## Migration guidance
- move defect-finding and remediation tickets into `critic`
- move acceptance checks and completion authority into `verifier`
- keep final terminal-state ownership with the primary agent
