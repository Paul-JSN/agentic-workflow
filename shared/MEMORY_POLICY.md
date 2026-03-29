# Memory Policy

This contract defines what information may be retained, for how long, and in what form.

## Memory layers
| Layer | Purpose |
| --- | --- |
| Session memory | short-lived context needed to finish the current task |
| Working memory | reusable summaries, decisions, and constraints for active work |
| Durable memory | intentionally retained information for future sessions |

## Retention rules
- Retain the minimum information needed for continuity.
- Prefer summaries over raw transcripts.
- Avoid storing secrets, credentials, payment data, or regulated personal data in long-lived memory.
- Store decisions, stable preferences, and confirmed constraints only when they materially improve future work.

## Freshness rules
- Time-sensitive facts should include a date or freshness marker.
- Assumptions should not be promoted to durable memory.
- If a remembered fact is likely stale or high impact, verify it before relying on it.

## Privacy and safety
- Sensitive material follows `{{SENSITIVE_DATA_RULES}}`.
- If retention is uncertain or potentially inappropriate, minimize storage and escalate if needed.

## Deletion and correction
- Incorrect memory should be corrected at the first reliable opportunity.
- Obsolete memory should be removed or marked stale when it no longer serves a valid purpose.
