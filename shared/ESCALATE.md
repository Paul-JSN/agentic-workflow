# `/escalate` Escalation

The `/escalate` marker is the standard escalation block for approval, policy, risk, or uncertainty stops.

## Use `/escalate` when
- approval is required before the next action
- policy interpretation is unclear
- the task may cause harm, data loss, or external impact
- the request is materially ambiguous and guessing would change the outcome
- the role cannot bound a subagent task safely
- the available tools or permissions do not clearly match the requested action

## Behavior on escalation
- state-changing work pauses
- safe evidence gathering may continue only if it stays inside the disputed boundary
- ask for the **smallest decision needed** to resume
- avoid stacking multiple unresolved risks into one escalation when separate decisions would be clearer

## Standard block
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
Once an `/escalate` item is resolved, resume from the last safe state and report what changed.
