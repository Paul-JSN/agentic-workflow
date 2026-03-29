# agentic-workflow

A reusable OpenClaw orchestration pack for building structured multi-agent workflows.

This repo is a generic, public-facing pack of shared contracts, role templates, starter bundles, and handoff snippets. It is designed for operators who want stronger approval boundaries, bounded delegation, explicit verification, and cleaner multi-agent coordination without hard-coding one person's private setup.

## Design goals
- approval-first execution for new work
- bounded delegation instead of vague worker swarms
- explicit critique and verification lanes for higher-trust completion
- anti-fake-done completion rules
- generic role contracts that can be customized locally
- concise, evidence-based reporting and escalation

## Role model
- `primary-agent` — coordinator, intake owner, final release owner
- `planner` — task decomposition and approval-gate planning
- `researcher` — evidence gathering and uncertainty reduction
- `executor` — implementation and scoped action
- `critic` — concrete defect tickets and gap analysis
- `verifier` — acceptance checks and objective-level completion verification

## Directory layout
```text
agent-os-pack/
├── README.md
├── START-HERE.md
├── COPY-THIS-PROMPT.md
├── INTERNAL-BUNDLE-PICKER.md
├── shared/
│   ├── APPROVAL_BOUNDARIES.md
│   ├── ESCALATE.md
│   ├── MEMORY_POLICY.md
│   ├── ORCHESTRATION.md
│   ├── PLACEHOLDERS.md
│   ├── QUESTION_ROUTING.md
│   ├── REPORTING_CONTRACT.md
│   └── VOICE_SYSTEM.md
├── packs/
│   ├── core/
│   │   ├── primary-agent/
│   │   ├── planner/
│   │   ├── researcher/
│   │   ├── executor/
│   │   ├── critic/
│   │   └── verifier/
│   ├── support/
│   └── vertical/
├── starter-bundles/
│   ├── MINIMAL.md
│   ├── STANDARD.md
│   ├── RESEARCH-HEAVY.md
│   ├── QUALITY-CRITICAL.md
│   └── MARKETING-STARTER.md
├── snippets/
└── examples/
```

## Start here
If you want the smallest clean entry path:
1. read `START-HERE.md`
2. use `COPY-THIS-PROMPT.md`
3. let the primary agent recommend the smallest suitable starter bundle
4. approve before any files are applied

## Philosophy in one paragraph
This pack assumes that planning is not completion, worker-reported completion is not objective completion, and execution should stay bounded until evidence says the objective is actually done. The primary agent owns coordination and release decisions. Specialists help, but they do not silently redefine scope or self-certify final success.

## Customization flow
1. Replace placeholders from `shared/PLACEHOLDERS.md`.
2. Tighten `shared/APPROVAL_BOUNDARIES.md` for your deployment.
3. Set delegation and job-state rules in `shared/ORCHESTRATION.md`.
4. Pick the smallest viable starter bundle.
5. Add support or vertical roles only when they clearly help.
6. Test with dry-run scenarios before production use.

## Notes
- The `reviewer` role is kept only as a migration bridge; new deployments should prefer `critic` + `verifier`.
- The pack is intentionally generic. Local naming, private files, and operator-specific habits should stay outside the public baseline.
