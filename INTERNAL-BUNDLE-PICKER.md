# Internal Bundle Picker

This file helps the primary agent choose the **smallest suitable starter bundle** for the operator's current goal.

> [!NOTE]
> This is reference material for the primary agent, not the beginner front door.

## Decision rule
Pick the **smallest bundle that can reliably complete the job**.
Do not add extra roles unless the task clearly needs them.

## Selection factors
- task complexity
- research load
- failure cost
- verification strictness
- whether critique tickets are needed before acceptance

## Bundle matrix
| Bundle | Best for | Includes |
| --- | --- | --- |
| `MINIMAL` | simple direct work with low overhead | primary-agent, executor, verifier |
| `STANDARD` | repeated multi-step work | primary-agent, planner, executor, verifier |
| `RESEARCH-HEAVY` | evidence-first work | primary-agent, planner, researcher, executor, verifier |
| `QUALITY-CRITICAL` | failure-sensitive or overclaim-prone work | primary-agent, planner, executor, critic, verifier |
| `MARKETING-STARTER` | messaging and campaign work | primary-agent, planner, executor, verifier, marketing-strategist |

## Bundle details

### 1) Minimal
**Use when**
- the work is short or moderate in scope
- the operator mainly needs one reliable helper
- most tasks are direct execution, drafting, or local organization
- a lightweight verification lane is enough

**Avoid when**
- the work needs explicit planning
- the work needs significant research
- failure cost is high enough that critique should happen before final acceptance

### 2) Standard
**Use when**
- the work is multi-step
- the operator wants clearer planning and verification
- tasks often involve drafting, execution, and checking
- the system should stay simple but more structured than Minimal

**Avoid when**
- the task is truly simple enough for Minimal
- the main effort is gathering and evaluating outside information
- the task needs explicit critique tickets before release

### 3) Research-Heavy
**Use when**
- the task depends on evidence gathering or comparison
- uncertainty is high
- the operator wants sourced findings before action
- recommendations need stronger factual grounding

**Avoid when**
- the task is mostly direct execution with little fact-finding
- critique and repair loops matter more than research depth

### 4) Quality-Critical
**Use when**
- the task is failure-sensitive, public-facing, expensive to redo, or easy to overclaim
- the operator wants explicit critique before final verification
- the system should catch “completed but not actually done” states more aggressively

**Optional add-on**
- add `researcher` if evidence gathering is central

### 5) Marketing Starter
**Use when**
- the task is positioning, messaging, campaign planning, or marketing content direction
- domain-specific marketing judgment is useful
- the operator still wants a small coordinated system

**Avoid when**
- the task is not meaningfully marketing-related

## Expected output from the primary agent
- recommended bundle
- why it fits
- roles included
- optional roles not chosen
- one approval question before application
