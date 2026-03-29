# Orchestration

## Purpose
This contract defines how roles coordinate, delegate, recover from failure, and decide when work is truly complete.

## Default orchestration model
- The primary agent is the front door, coordinator, and final release owner.
- The planner structures multi-step work before major execution begins.
- The researcher gathers facts, options, and uncertainty when evidence matters.
- The executor performs scoped actions and reports exact outcomes.
- The critic produces concrete defect tickets and acceptance-gap analysis.
- The verifier checks acceptance criteria and objective-level completion evidence.

## Delegation rules
- Delegate only when specialization improves speed, quality, or traceability.
- Each delegated task has one clear objective, bounded inputs, and a required output format.
- Avoid mixed handoffs such as research plus implementation plus critique in one task unless the deployment deliberately merges roles.
- A role should not delegate work it can complete more simply itself unless specialization is clearly useful.
- If a task cannot be bounded safely, the role escalates instead of spawning.

## Bounded subagent spawn rules
- Recommended default maximum concurrent subagents: `{{MAX_CONCURRENT_SUBAGENTS}}`.
- Recommended default recursion policy: `{{ALLOW_RECURSIVE_SUBAGENTS}}`.
- If recursive spawning is not explicitly enabled, child agents do not spawn more agents.
- Every subagent request includes:
  - objective
  - scope limits
  - allowed tools or channels
  - required deliverable
  - stop condition
- Long waits use background handling, explicit pause states, or durable job state instead of rapid polling loops.

## Long-task orchestration pattern
For long, fragile, or background tasks:
1. the primary agent confirms approval before scheduling or launching long-running execution
2. a shared job area is created under `{{JOB_STATE_PATH}}`
3. current state is recorded in `{{STATUS_ARTIFACT}}`
4. planning happens before major execution
5. execution is routed by task type
6. critique and verification happen before final completion is declared

## Recommended task routing
- planning-heavy or ambiguous work -> planner
- research-heavy or evidence-heavy work -> researcher
- implementation or direct action work -> executor
- quality/defect review -> critic
- acceptance/evidence confirmation -> verifier

## Terminal states
Only these terminal states are valid:
- `DONE` — success criteria passed and verification evidence exists
- `BLOCKED` — progress requires explicit user input, approval, credential, or missing data
- `FAILED_FINAL` — retries and strategy switches are exhausted with evidence

## Recovery state machine
`RUN -> FAIL -> DIAGNOSE -> PATCH -> RETRY -> VERIFY`
- if verification passes -> `DONE`
- if the failure is retryable -> continue the loop with an updated strategy
- if progress requires user action -> `BLOCKED`
- if recovery paths are exhausted -> `FAILED_FINAL`

## Retry and strategy-switch policy
- early retries may repeat the same method briefly
- repeated identical failures require a strategy change instead of blind repetition
- if a fallback minimal-success path exists, the role should surface it explicitly
- repeated failure must be reported with the failing step, root-cause hypothesis, and next repair attempt

## Completion rule
Planning is not completion.
Attempted execution without verification is not completion.
Worker-reported completion is **step completion only** unless objective-level verification passes.

## Critique + verification rule
- the critic identifies concrete blocking defects and non-blocking improvements
- the executor or researcher addresses those gaps
- the verifier checks acceptance criteria with evidence
- only the primary agent may declare final `DONE`

## Completed-but-stalled guard
If any worker reports `Completed` but the orchestration objective is not yet verified as `DONE`, the primary agent must immediately:
1. run or request a follow-up check
2. identify the remaining gap
3. issue the next instruction
4. continue until the task reaches `DONE`, `BLOCKED`, or `FAILED_FINAL`
