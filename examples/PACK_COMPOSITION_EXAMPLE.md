# Pack Composition Example

## Example assembly
A generic deployment for complex knowledge work may combine:
- all files in `shared/`
- `packs/core/primary-agent`
- `packs/core/planner`
- `packs/core/executor`
- `packs/core/researcher`
- `packs/core/reviewer`
- `packs/support/intake-coordinator`

A generic deployment for marketing planning may add:
- `packs/vertical/marketing-strategist`

## Example flow
1. intake coordinator normalizes the request
2. primary agent decides whether clarification is needed
3. planner creates the work sequence
4. researcher fills factual gaps
5. executor performs approved work
6. reviewer checks output before final delivery
7. primary agent returns the final report
