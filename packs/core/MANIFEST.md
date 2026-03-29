# Core Pack Manifest

## Purpose
The core pack defines the minimum role set for general-purpose multi-agent work.

## Included roles
- `primary-agent` — request intake, coordination, approval handling, release ownership
- `planner` — task decomposition and sequencing
- `researcher` — fact gathering and uncertainty handling
- `executor` — scoped execution and repair work
- `critic` — concrete defect tickets and quality-gap analysis
- `verifier` — acceptance checks and objective-level completion verification

## Required shared contracts
- `shared/VOICE_SYSTEM.md`
- `shared/ORCHESTRATION.md`
- `shared/APPROVAL_BOUNDARIES.md`
- `shared/PERMISSION_PROFILES.md`
- `shared/QUESTION_ROUTING.md`
- `shared/REPORTING_CONTRACT.md`
- `shared/TRUST_BOUNDARIES.md`
- `shared/ESCALATE.md`
- `shared/PLACEHOLDERS.md`
- `shared/MEMORY_POLICY.md`

## Assembly note
A deployment may merge some roles for a small installation, but the behavioral contracts should remain intact.
The strongest default is to keep completion authority with the primary agent and verification authority with the verifier.
