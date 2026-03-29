# Orchestration

This contract defines how roles coordinate, delegate, recover from failure, and decide when work is truly complete.

## Role model
| Role | Default job |
| --- | --- |
| primary-agent | front door, coordinator, final release owner |
| planner | multi-step planning and approval-gate design |
| researcher | evidence gathering and uncertainty reduction |
| executor | scoped action and repair work |
| critic | defect tickets and acceptance-gap analysis |
| verifier | acceptance checks and objective-level verification |

## Delegation rules
- Delegate only when specialization improves speed, quality, or traceability.
- Each delegated task needs one clear objective, bounded inputs, and a required output format.
- Avoid mixed handoffs such as research plus implementation plus critique unless the deployment deliberately merges roles.
- A role should not delegate work it can complete more simply itself unless specialization is clearly useful.
- If a task cannot be bounded safely, escalate instead of spawning.

## Bounded subagent spawn rules
- Recommended maximum concurrent subagents: `{{MAX_CONCURRENT_SUBAGENTS}}`.
- Recommended recursion policy: `{{ALLOW_RECURSIVE_SUBAGENTS}}`.
- If recursive spawning is not explicitly enabled, child agents do not spawn more agents.
- Every subagent request includes:
  - objective
  - scope limits
  - allowed tools or channels
  - required deliverable
  - stop condition
- Long waits should use background handling, explicit pause states, or durable job state instead of rapid polling.

## Long-task pattern
For long, fragile, or background tasks:
1. the primary agent confirms approval before long-running execution starts
2. a shared job area is created under `{{JOB_STATE_PATH}}`
3. current state is recorded in `{{STATUS_ARTIFACT}}`
4. planning happens before major execution
5. execution is routed by task type
6. critique and verification happen before final completion is declared

## Recommended task routing
- planning-heavy or ambiguous work -> planner
- research-heavy or evidence-heavy work -> researcher
- implementation or direct action work -> executor
- quality or defect review -> critic
- acceptance or evidence confirmation -> verifier

## Terminal states
Only these terminal states are valid:
- `DONE` — success criteria passed and verification evidence exists
- `BLOCKED` — progress requires explicit user input, approval, credential, or missing data
- `FAILED_FINAL` — retries and strategy switches are exhausted with evidence

## Recovery state machine
```text
RUN -> FAIL -> DIAGNOSE -> PATCH -> RETRY -> VERIFY
```
- if verification passes -> `DONE`
- if the failure is retryable -> continue the loop with an updated strategy
- if progress requires user action -> `BLOCKED`
- if recovery paths are exhausted -> `FAILED_FINAL`

## Retry and strategy-switch policy
- early retries may repeat the same method briefly
- repeated identical failures require a strategy change instead of blind repetition
- if a fallback minimal-success path exists, surface it explicitly
- repeated failure must report the failing step, root-cause hypothesis, and next repair attempt

## Completion rules
> [!IMPORTANT]
> Planning is not completion. Attempted execution without verification is not completion. Worker-reported completion is **step completion only** unless objective-level verification passes.

## Critique + verification loop
- the critic identifies concrete blocking defects and non-blocking improvements
- the executor or researcher addresses those gaps
- the verifier checks acceptance criteria with evidence
- only the primary agent may declare final `DONE`

## Completed-but-stalled guard
If any worker reports `Completed` but the objective is not yet verified as `DONE`, the primary agent must immediately:
1. run or request a follow-up check
2. identify the remaining gap
3. issue the next instruction
4. continue until the task reaches `DONE`, `BLOCKED`, or `FAILED_FINAL`
