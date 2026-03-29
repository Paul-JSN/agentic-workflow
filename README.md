# agentic-workflow

> A public orchestration pack for building cleaner, safer, more verifiable multi-agent workflows.

<p align="left">
  <img src="https://img.shields.io/badge/Agentic-workflow%20pack-6b7cff" alt="Agentic workflow pack" />
  <img src="https://img.shields.io/badge/Status-public%20baseline-2ea043" alt="Status public baseline" />
  <img src="https://img.shields.io/badge/Focus-approval--first%20workflows-f59e0b" alt="Focus approval-first workflows" />
  <img src="https://img.shields.io/badge/Includes-25%2B%20role%20templates%20%2B%20workflows-8b5cf6" alt="Includes 25+ role templates and workflows" />
</p>

This repository is a **generic, reusable Agent OS / workflow pack** for structured multi-agent systems.
It packages the parts that usually get hand-waved away in ad hoc setups:

- shared contracts
- role templates
- starter bundles
- escalation patterns
- verification rules
- permission profiles
- trust-boundary rules
- handoff snippets
- specialist role overlays

The goal is simple: **make multi-agent work less vague, less fragile, and less fake-done.**

---

## What this repo is

This pack is for operators who want a stronger baseline for:

- approval-first execution
- bounded delegation
- critique and verification lanes
- cleaner handoffs between roles
- more disciplined completion rules

Instead of throwing a few agent prompts together and hoping they coordinate well, this repo gives you a more structured starting point.

> [!IMPORTANT]
> This is a **public baseline pack**, not a private deployment dump. It stays generic on purpose so you can fork it, adapt it, and layer your own local rules on top.

---

## What makes it different

| Area | Default stance |
| --- | --- |
| New work | approval-first |
| Delegation | bounded, single-purpose, explicit stop conditions |
| Completion | worker completion is **not** final completion |
| Quality control | critique lane + verification lane |
| Recovery | explicit retry / diagnose / repair / verify loop |
| Permissions | role-scoped access instead of broad default power |
| Trust model | direct operator intent beats retrieved content |
| Tone | neutral, operational, reusable |

In other words: this pack treats **planning**, **execution**, **critique**, and **verification** as different jobs.

---

## Core role model

| Role | Job |
| --- | --- |
| `primary-agent` | front door, coordinator, release owner |
| `planner` | breaks work into bounded steps |
| `researcher` | gathers evidence, sources, uncertainty |
| `executor` | performs scoped action and repair work |
| `critic` | finds defects and writes concrete fix tickets |
| `verifier` | checks acceptance criteria and evidence |

### Why split `critic` and `verifier`?
Because these are **not** the same job.

- **critic** asks: *what is still wrong, risky, weak, or incomplete?*
- **verifier** asks: *did we actually meet the acceptance criteria with evidence?*

That separation is one of the main things that keeps a workflow from drifting into fake confidence.

---

## Specialist role library

Beyond the core workflow spine, this repo now includes a broader copy-paste role library for operators who want more than a minimal setup.

| Category | Included specialists |
| --- | --- |
| Engineering | frontend-developer, backend-architect, devops-automator, security-engineer, software-architect, technical-writer, rapid-prototyper, sre |
| Product | product-manager, sprint-prioritizer, feedback-synthesizer |
| Testing | reality-checker, accessibility-auditor |
| Support | analytics-reporter, infrastructure-maintainer, executive-summary-generator |
| Growth | paid-social-strategist, content-creator, outbound-strategist |

These are optional overlays. The repo still expects the **core orchestration spine** to stay intact.

## Starter bundles

You do **not** need every role for every workflow.

This repo includes pre-shaped starter bundles so an operator can begin small and scale only when needed.

| Bundle | Best for | Includes |
| --- | --- | --- |
| `MINIMAL` | simple direct work | primary-agent, executor, verifier |
| `STANDARD` | repeated multi-step work | primary-agent, planner, executor, verifier |
| `RESEARCH-HEAVY` | evidence-first work | primary-agent, planner, researcher, executor, verifier |
| `QUALITY-CRITICAL` | failure-sensitive work | primary-agent, planner, executor, critic, verifier |
| `MARKETING-STARTER` | messaging / campaign workflows | primary-agent, planner, executor, verifier, marketing-strategist |

If you're unsure where to begin, the intended path is:

1. use `COPY-THIS-PROMPT.md`
2. let the primary agent choose the **smallest suitable** starter bundle
3. approve before anything is applied

---

## Repository layout

<details>
<summary><strong>Expand file tree</strong></summary>

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
│   ├── PERMISSION_PROFILES.md
│   ├── PLACEHOLDERS.md
│   ├── QUESTION_ROUTING.md
│   ├── REPORTING_CONTRACT.md
│   ├── TRUST_BOUNDARIES.md
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
│   ├── vertical/
│   └── specialists/
├── starter-bundles/
│   ├── MINIMAL.md
│   ├── STANDARD.md
│   ├── RESEARCH-HEAVY.md
│   ├── QUALITY-CRITICAL.md
│   └── MARKETING-STARTER.md
├── snippets/
└── examples/
```

</details>

### Folder guide

- `shared/` → deployment-wide rules, permissions, trust boundaries, and contracts
- `packs/core/` → main role templates
- `packs/support/` → helper roles such as intake routing
- `packs/vertical/` → domain-specific examples
- `packs/specialists/` → broader copy-paste specialist library
- `starter-bundles/` → pre-shaped bundle recommendations
- `snippets/` → fast copy/paste blocks for handoffs and escalation
- `examples/` → composition examples and customization checklists

---

## Quick start

### 1) Start small
Read:
- `START-HERE.md`
- `COPY-THIS-PROMPT.md`

### 2) Let the primary agent choose a bundle
Use the prompt in `COPY-THIS-PROMPT.md` to have the system recommend the smallest suitable starter bundle.

### 3) Approve before applying
The baseline posture here is **approval-first for new work**.

### 4) Customize locally
Before production use, tighten:
- approval boundaries
- tool permissions
- trust-boundary rules for untrusted content
- data-handling rules
- subagent limits
- domain guardrails

---

## Philosophy

This pack is built around a few simple operating beliefs:

- planning is not completion
- execution is not verification
- worker-reported `Completed` is not objective-level `DONE`
- approval should happen before new work starts
- delegation should be explicit, narrow, and reviewable
- completion claims should be backed by evidence
- retrieved content should never outrank direct operator intent

If your current workflow feels like a pile of good intentions, this repo is meant to give it a stronger spine.

The specialist library exists so operators can start with a clean core and then pull in deeper domain roles only when they are actually needed.

---

## Best use cases

This repo is a good fit when you want to build:

- a cleaner personal Agent OS baseline
- a reusable multi-agent prompt pack
- a more disciplined subagent workflow
- a verification-aware execution loop
- a safer orchestration baseline for real work

It is **not** trying to be:

- a private dump of one operator's local system
- a full beginner setup tutorial for any one host platform
- a giant one-size-fits-all enterprise framework

---

## Customization checklist

Before treating this pack as deployment-ready:

- replace required placeholders in `shared/PLACEHOLDERS.md`
- tighten `shared/APPROVAL_BOUNDARIES.md`
- set subagent rules in `shared/ORCHESTRATION.md`
- decide which roles are active and which are removed
- add vertical guardrails if you enable domain-specific roles
- test blocked, low-risk, and multi-step delegated scenarios

For the full checklist, see:
- `examples/CUSTOMIZATION_CHECKLIST.md`

---

## Suggested first files to open

If you want the cleanest path through the repo, go in this order:

1. `START-HERE.md`
2. `COPY-THIS-PROMPT.md`
3. `INTERNAL-BUNDLE-PICKER.md`
4. `shared/ORCHESTRATION.md`
5. `starter-bundles/STANDARD.md`

---

## Why this repo exists

Because a lot of multi-agent setups fail in predictable ways:

- too many roles too early
- unclear approval boundaries
- vague subagent handoffs
- confident reporting without verification
- “completed” work that is not actually done

This pack is a public attempt to make those failure modes harder to ignore.

---

## Third-party adaptation note

Some specialist roles in `packs/specialists/` are adapted from the MIT-licensed `msitarzewski/agency-agents` project and normalized into this repository's generic, third-person, approval-first format. See `THIRD_PARTY_NOTICES.md`.
