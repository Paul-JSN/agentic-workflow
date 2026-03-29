# Customization Checklist

- Replace all required placeholders in `shared/PLACEHOLDERS.md`.
- Set `{{MAX_CONCURRENT_SUBAGENTS}}` and `{{ALLOW_RECURSIVE_SUBAGENTS}}`.
- Tighten the approval policy for live systems, external channels, and destructive actions.
- Add deployment-specific data handling rules to `{{SENSITIVE_DATA_RULES}}`.
- Confirm which roles are active and which roles are removed.
- Add vertical guardrails before enabling any domain-specific role.
- Test `/escalate` escalation with at least one approval-needed scenario.
- Test a blocked scenario, a low-risk autonomous scenario, and a multi-step delegated scenario.
