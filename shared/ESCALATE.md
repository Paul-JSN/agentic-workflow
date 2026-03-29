# `/escalate` Escalation

## Purpose
The `/escalate` marker is the standard escalation block for approval, policy, risk, or uncertainty stops.

## When `/escalate` is used
- approval is required before the next action
- policy interpretation is unclear
- the task may cause harm, data loss, or external impact
- the request is materially ambiguous and guessing would change the outcome
- the role cannot bound a subagent task safely
- the available tools or permissions do not clearly match the requested action

## Behavior on escalation
- state-changing work pauses
- safe evidence gathering may continue only if it does not cross the disputed boundary
- the role asks for the smallest decision needed to resume
- the role avoids stacking multiple unresolved risks into one escalation when separate decisions would be clearer

## Standard `/escalate` block
```text
/escalate
reason: <why the task is paused>
blocked_action: <what cannot proceed>
risk: <primary risk or uncertainty>
options:
  1. <lowest-risk path>
  2. <alternate path>
recommended_next_step: <preferred decision>
```

## Resolution rule
Once a `/escalate` item is resolved, the role resumes from the last safe state and reports what changed.
