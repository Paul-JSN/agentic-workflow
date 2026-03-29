# Research-Heavy Starter Bundle

## Use when
- the task depends on outside evidence, comparison, or uncertainty reduction
- the operator wants sourced findings before action
- recommendations need stronger factual grounding

## Include first
- all shared contracts
- `packs/core/primary-agent/TEMPLATE.md`
- `packs/core/planner/TEMPLATE.md`
- `packs/core/researcher/TEMPLATE.md`
- `packs/core/executor/TEMPLATE.md`
- `packs/core/verifier/TEMPLATE.md`

## Why this bundle exists
This bundle keeps the standard coordination flow but adds a dedicated research lane.
That reduces the chance that execution and evidence gathering get mixed together.

## What stays out for now
- critic unless critique and repair loops are clearly needed
- vertical roles unless the work is clearly domain-specific

## Upgrade path
If the task is specifically marketing-oriented, consider `MARKETING-STARTER.md`.
If failure cost is high, consider layering in `QUALITY-CRITICAL.md`.
