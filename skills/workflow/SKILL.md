---
name: workflow
description: Runs the phased development workflow and session lifecycle. Handles ideation gates, interface strawmen, interface-first development, contract tests, phase completion, and session snapshot management (.ai-memory/handoff.md). Use when starting, resuming, or finishing a development phase or session.
disable-model-invocation: false
---

# Skill: Phased Workflow & Session Lifecycle

## Objective

Execute the rigorous multi-step development workflow, maintain strict separation between internal sessional memory and user-facing documentation (`README.md`, `AGENTS.md`, `PROGRESS.md`, `DEVELOPMENT_PLAN.md`), and manage session persistence via `.ai-memory/handoff.md`.

## 1. Session Initialization & Continuity (Start of Iteration / Session)

At the very beginning of any session or new iteration, read the following internal and user-facing state files:
1. **`.ai-memory/misconceptions.md`**: Active tool warnings, schema notes, and command patterns.
2. **`PROGRESS.md`**: Current phase, active step, and open decisions.
3. **`.ai-memory/handoff.md`**: Sessional thinking mnemonic snapshot, key trade-offs, and current mental model from the previous session.
4. **`DEVELOPMENT_PLAN.md`**: Overall roadmap and phase requirements.

## 2. Session Finalization & Snapshot (End of Session / Phase End)

Whenever a session concludes or a phase successfully closes:
- Consolidate the current technical state, architectural insights, open loops, and key trade-offs.
- Write/update the mnemonic snapshot in **`.ai-memory/handoff.md`**.
- Keep user-facing files (`README.md`, `AGENTS.md`, `PROGRESS.md`, `DEVELOPMENT_PLAN.md`) strictly focused on permanent documentation and milestone tracking without internal sessional bloat.

## 3. Phased Development Pipeline (`DEVELOPMENT_PLAN.md`)

### Step 0: Orient
1. Read `PROGRESS.md` (current phase, step, open decisions).
2. Read the active phase section in `DEVELOPMENT_PLAN.md`, plus Appendix A (interface strawmen).
3. Skim target packages if they exist.

### Step 1: Ideation — HARD GATE
Produce an ideation brief and stop:
- Working principles for this phase (2–5 bullets).
- Interface strawman: concrete signatures starting from Appendix A and the phase's Step 2 list.
- Numbered questions for everything genuinely open (phase Step 1 list + relevant `PROGRESS.md` open decisions).
- Risks or platform divergences foreseen.

*Present it and wait. Do not create or modify anything.*
On approval: log decisions in `PROGRESS.md`, clear resolved open decisions, set `Current step` to `interfaces`.

### Step 2: Interfaces
Land compile-only types in the target package(s) per the approved strawman. No runtime logic. Run lint, vet, typecheck commands present at project. Update `PROGRESS.md`.

### Step 3: Tests
From the phase's Step 3 list: happy path + edge cases, written against interfaces only.
- Include inference tests for curried factories.
- Wire contract suites against local/stubbed platform.
- Tests may be red; main merges only when green. Update `PROGRESS.md`.

### Step 4: Interface Approval — GATE
Show the user the landed public surface (exported names + signatures, diffed against strawman). Implementation does not start until user approves. On approval, set `Current step` to `implementation`.

### Step 5: Implementation
Fulfill interfaces until green: lint, vet, typecheck, test, build. Obey `AGENTS.md`.
If implementation proves an interface wrong: **stop coding**, propose amendment back at step 4 with rationale. Never silently change an approved interface.

### Step 6: Close the Phase
1. Verify phase exit criteria (`DEVELOPMENT_PLAN.md`, "Workflow contract").
2. Update `PROGRESS.md`: tick phase, set next current phase, update last completed.
3. Report: what landed, test status, deviations from strawman, follow-ups.
4. Update `.ai-memory/handoff.md` with phase closure insights.
5. Offer — do not perform — a conventional commit (type/scope rules in `AGENTS.md`).
