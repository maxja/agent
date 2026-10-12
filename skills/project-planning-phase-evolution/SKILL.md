---
name: project-planning-phase-evolution
description: Guides project definitions through a structured, phased progression. Ensures project complexity and dependencies grow strictly through verifiable milestones.
disable-model-invocation: false
---

# Skill: Project Planning & Phased Evolution

## Objective

Define project scope and architect a phased evolution where each subsequent phase introduces higher complexity and dependencies upon earlier verified phases.

## Guidelines

1. **Uncertainty & Solutions:**
   - If project details, constraints, or goals are ambiguous, explicitly ask the user for clarification.
   - Always propose 1–2 concrete, recommended solutions alongside your question to minimize back-and-forth.
2. **Phase Design Rules:**
   - **Incremental Complexity:** Phase $N+1$ must build directly on the foundation verified in Phase $N$.
   - **Explicit Verification Gate:** Every phase MUST include a explicit, measurable verification criteria (e.g., unit/integration test suite passing, concrete functional demonstration).
   - **No Unverified Assumptions:** Do not proceed to outline step-level execution for future phases until the current phase's verification criteria are met.

## Execution Template

### 1. Project Definition

- **Core Vision:** Brief summary of project purpose.
- **Key Constraints & Tech Stack:** Identified constraints and technology choices.
- **Uncertainties & Proposed Options:** (If applicable) Clarifying questions with recommended solutions.

### 2. Evolutionary Roadmap

#### Phase 1: Core Foundation (Low Complexity)

- **Goal:** [Primary focus]
- **Dependencies:** None
- **Key Deliverables:** [Concrete outputs]
- **Verification Criteria:** [Explicit steps or tests to prove completion]

#### Phase 2: Functional Expansion (Medium Complexity)

- **Goal:** [Primary focus]
- **Dependencies:** Phase 1 (Verified)
- **Key Deliverables:** [Concrete outputs]
- **Verification Criteria:** [Explicit steps or tests to prove completion]

#### Phase N: Advanced Integration & Polish (High Complexity)

- **Goal:** [Primary focus]
- **Dependencies:** Phase N-1 (Verified)
- **Key Deliverables:** [Concrete outputs]
- **Verification Criteria:** [Explicit steps or tests to prove completion]
