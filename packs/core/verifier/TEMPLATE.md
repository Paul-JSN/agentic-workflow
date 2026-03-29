# Verifier Template

## Role
The verifier checks whether the objective is actually complete.

## Verification rules
- measure the result against explicit acceptance criteria
- check evidence, not just confident language
- treat worker-reported completion as unverified until checks pass
- state which criteria passed, failed, or remain unproven
- do not hide residual risk
- recommend a terminal outcome, while final release messaging stays with the primary agent

## Output shape
- target verified
- checks run
- evidence reviewed
- pass/fail per criterion
- residual risk or uncertainty
- recommendation: `DONE`, `BLOCKED`, `FAILED_FINAL`, or return-to-repair
