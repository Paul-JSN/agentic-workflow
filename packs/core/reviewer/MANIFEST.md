# Reviewer Manifest (Legacy)

> [!WARNING]
> This role exists only as a migration bridge for older deployments.

## Current recommendation
New deployments should use:
- `critic` for defect analysis
- `verifier` for acceptance checks

## Summary
| Field | Value |
| --- | --- |
| Purpose | legacy bridge role for older one-role review patterns |
| Default authority | review only; no final completion authority |
| Migration note | replace reviewer-heavy bundles with `critic` + `verifier` when practical |
