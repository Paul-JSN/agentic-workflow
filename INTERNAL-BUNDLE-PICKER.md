# Internal Bundle Picker

## Purpose
This file helps the primary agent choose the smallest suitable starter bundle for the operator's current goal. It is reference material for the primary agent, not the beginner front door.

## Decision rule
Pick the **smallest bundle that can reliably complete the job**.
Do not add extra roles unless the task clearly needs them.

Primary decision factors:
- task complexity
- research load
- failure cost
- verification strictness
- whether critique or review tickets are necessary before acceptance

## Bundle options
### 1) Minimal
Use when:
- the work is short or moderate in scope
- the operator mainly needs one reliable helper
- most tasks are direct execution, drafting, or local organization
- a lightweight verification lane is still enough

Includes:
- shared contracts
- primary-agent
- executor
- verifier

Avoid when:
- the work needs explicit planning
- the work needs significant research
- the task has enough failure cost that critique should happen before final acceptance

### 2) Standard
Use when:
- the work is multi-step
- the operator wants clearer planning and verification
- tasks often involve drafting, execution, and checking
- the system should stay simple but more structured than Minimal

Includes:
- shared contracts
- primary-agent
- planner
- executor
- verifier

Avoid when:
- the task is truly simple enough for Minimal
- the main effort is gathering and evaluating outside information
- the task needs explicit critique tickets before release

### 3) Research-Heavy
Use when:
- the task depends on evidence gathering or comparison
- uncertainty is high
- the operator wants sourced findings before action
- recommendations need stronger factual grounding

Includes:
- shared contracts
- primary-agent
- planner
- researcher
- executor
- verifier

Avoid when:
- the task is mostly direct execution with little fact-finding
- critique and repair loops are more important than research depth

### 4) Quality-Critical
Use when:
- the task is failure-sensitive, public-facing, expensive to redo, or easy to overclaim
- the operator wants explicit critique before final verification
- the system should catch “completed but not actually done” states more aggressively

Includes:
- shared contracts
- primary-agent
- planner
- executor
- critic
- verifier

Optional add-on:
- researcher, if evidence gathering is central

Avoid when:
- the task is simple enough for Standard
- the extra quality lane would add more overhead than value

### 5) Marketing Starter
Use when:
- the task is positioning, messaging, campaign planning, or marketing content direction
- domain-specific marketing judgment is useful
- the operator still wants a small coordinated system

Includes:
- shared contracts
- primary-agent
- planner
- executor
- verifier
- marketing-strategist

Avoid when:
- the task is not meaningfully marketing-related

## Output expected from the primary agent
The primary agent should return:
- recommended bundle
- why it fits
- roles included
- optional roles not chosen
- one approval question before application
