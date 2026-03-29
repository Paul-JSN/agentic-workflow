# Placeholders

## Purpose
This file defines common placeholders used throughout the pack.

## Formatting rule
Placeholders use double curly braces, such as `{{ORG_NAME}}`.

## Common placeholders
| Placeholder | Meaning |
| --- | --- |
| `{{ORG_NAME}}` | organization or team name |
| `{{DEPLOYMENT_NAME}}` | local name of the agent deployment |
| `{{PRIMARY_GOAL}}` | the main business or operational objective |
| `{{VOICE_VARIANT}}` | optional tone narrowing, if any |
| `{{MAX_CONCURRENT_SUBAGENTS}}` | maximum number of parallel subagents allowed |
| `{{ALLOW_RECURSIVE_SUBAGENTS}}` | whether child agents may spawn additional agents |
| `{{ALLOWED_TOOLS}}` | tools approved for the role or deployment |
| `{{RESTRICTED_TOOLS}}` | tools or channels that are blocked |
| `{{DEFAULT_APPROVER}}` | human approval contact or function |
| `{{OUTPUT_DESTINATIONS}}` | where finished artifacts should be delivered |
| `{{SENSITIVE_DATA_RULES}}` | handling rules for confidential or regulated data |
| `{{DOMAIN_GUARDRAILS}}` | vertical-specific restrictions or quality rules |
| `{{APPROVAL_EXCEPTIONS}}` | explicit exceptions to the default approval policy |
| `{{RESTRICTED_SYSTEMS}}` | systems requiring additional care or approval |
| `{{JOB_STATE_PATH}}` | path to the shared job folder or task-state area |
| `{{STATUS_ARTIFACT}}` | file name for the shared status artifact (for example `STATUS.json`) |

## Replacement guidance
- Unresolved placeholders are acceptable in a draft pack.
- Production use should replace or remove every placeholder that affects behavior.
- If a task depends on an unresolved placeholder, the role should escalate with `/escalate` instead of inventing a value.
