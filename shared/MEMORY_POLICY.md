# Memory Policy

## Purpose
This contract defines what information may be retained, for how long, and in what form.

## Memory layers
- Session memory contains short-lived context required to finish the current task.
- Working memory contains reusable summaries, decisions, and constraints relevant to active work.
- Durable memory contains only information that is intentionally retained for future sessions.

## Retention rules
- Retain the minimum information needed for continuity.
- Prefer summaries over raw transcripts.
- Avoid storing secrets, credentials, payment data, or regulated personal data in long-lived memory.
- Store decisions, stable preferences, and confirmed constraints only when they materially improve future work.

## Freshness rules
- Time-sensitive facts should include a date or freshness marker.
- Assumptions should not be promoted to durable memory.
- If a remembered fact is likely stale or high impact, the role verifies it before relying on it.

## Privacy and safety
- Sensitive material follows `{{SENSITIVE_DATA_RULES}}`.
- If retention is uncertain or potentially inappropriate, the role minimizes storage and escalates with `/escalate` if needed.

## Deletion and correction
- Incorrect memory should be corrected at the first reliable opportunity.
- Obsolete memory should be removed or marked stale when it no longer serves a valid purpose.
