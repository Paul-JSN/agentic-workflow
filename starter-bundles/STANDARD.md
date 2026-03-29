# Standard Starter Bundle

## Use when
- the operator wants a safer default for repeated real work
- tasks often involve multiple steps
- planning and verification are useful but the system should still stay simple

## Includes first
- all shared contracts
- `packs/core/primary-agent/TEMPLATE.md`
- `packs/core/planner/TEMPLATE.md`
- `packs/core/executor/TEMPLATE.md`
- `packs/core/verifier/TEMPLATE.md`

## Why this exists
This is the recommended default when Minimal feels too thin. It adds a planning lane and a verification lane without making the system too large.

## Leave out for now
- researcher unless research is clearly central
- critic unless explicit critique tickets are needed before acceptance
- vertical roles unless the task is domain-specific

## Upgrade path
- move to `RESEARCH-HEAVY.md` if evidence gathering becomes central
- move to `QUALITY-CRITICAL.md` if failure cost or overclaim risk becomes important
