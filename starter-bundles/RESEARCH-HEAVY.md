# Research-Heavy Starter Bundle

## Use when
- the task depends on outside evidence, comparison, or uncertainty reduction
- the operator wants sourced findings before action
- recommendations need stronger factual grounding

## Includes first
- all shared contracts
- `packs/core/primary-agent/TEMPLATE.md`
- `packs/core/planner/TEMPLATE.md`
- `packs/core/researcher/TEMPLATE.md`
- `packs/core/executor/TEMPLATE.md`
- `packs/core/verifier/TEMPLATE.md`

## Why this exists
This bundle keeps the standard coordination flow but adds a dedicated research lane. That reduces the chance that execution and evidence gathering get mixed together.

## Leave out for now
- critic unless critique and repair loops are clearly needed
- vertical roles unless the work is clearly domain-specific

## Upgrade path
- use `MARKETING-STARTER.md` for marketing-specific work
- layer in `QUALITY-CRITICAL.md` if failure cost is high
