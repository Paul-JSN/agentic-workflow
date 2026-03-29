# Standard Starter Bundle

## Use when
- the operator wants a safer default for repeated real work
- tasks often involve multiple steps
- planning and verification are useful but the system should still stay simple

## Include first
- all shared contracts
- `packs/core/primary-agent/TEMPLATE.md`
- `packs/core/planner/TEMPLATE.md`
- `packs/core/executor/TEMPLATE.md`
- `packs/core/verifier/TEMPLATE.md`

## Why this bundle exists
This is the recommended default when Minimal feels too thin.
It adds a planning lane and a verification lane without making the system too large.

## What stays out for now
- researcher unless research is clearly central
- critic unless explicit critique tickets are needed before acceptance
- vertical roles unless the task is domain-specific

## Upgrade path
If evidence gathering becomes important, move next to `RESEARCH-HEAVY.md`.
If failure cost or overclaim risk becomes important, move next to `QUALITY-CRITICAL.md`.
