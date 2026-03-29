# Permission Profiles

This contract defines generic permission profiles for role assignment.

## Profile types
| Profile | Default scope |
| --- | --- |
| `read-only` | read, search, analyze, compare, summarize |
| `safe-exec` | non-destructive commands, checks, transforms, and verification inside approved scope |
| `write + safe-exec` | file edits plus safe command execution inside approved scope |
| `external-action` | outbound posting, publishing, sending, or integration changes; always approval-gated |

## Recommended role mapping
| Role | Suggested profile |
| --- | --- |
| `primary-agent` | coordination only; external-action remains approval-gated |
| `planner` | `read-only` |
| `researcher` | `safe-exec` or `read-only`, depending on deployment |
| `executor` | `write + safe-exec` |
| `critic` | `read-only` |
| `verifier` | `safe-exec` |

## Rules
- Do not grant broad write access to every role by default.
- Keep the smallest permission set that still allows the role to do its job.
- External/state-changing actions remain approval-gated regardless of role.
- If a role needs more access than expected, that should be explicit in the deployment, not assumed by the base pack.
