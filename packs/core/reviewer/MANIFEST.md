# Reviewer Manifest (Legacy)

- **Purpose:** legacy bridge role kept for older deployments that still expect one combined review role
- **Current recommendation:** new deployments should use `critic` for defect analysis and `verifier` for acceptance checks
- **Default authority:** review only; no final completion authority
- **Migration note:** replace reviewer-heavy bundles with `critic` + `verifier` when practical
