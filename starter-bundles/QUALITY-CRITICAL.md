# Quality-Critical Starter Bundle

## Use when
- the task is expensive to redo, easy to overclaim, or operationally sensitive
- the operator wants explicit critique before final verification
- completed-but-stalled states are a real concern

## Includes first
- all shared contracts
- `packs/core/primary-agent/TEMPLATE.md`
- `packs/core/planner/TEMPLATE.md`
- `packs/core/executor/TEMPLATE.md`
- `packs/core/critic/TEMPLATE.md`
- `packs/core/verifier/TEMPLATE.md`

## Optional add-on
- `packs/core/researcher/TEMPLATE.md` when evidence gathering is central to the task

## Why this exists
This bundle adds a dedicated critique lane before verification. It is the strongest default when failure cost is high or when the deployment wants a stronger anti-fake-done posture.

## Leave out for now
- vertical roles unless the task is domain-specific
- extra support roles unless intake is clearly messy
