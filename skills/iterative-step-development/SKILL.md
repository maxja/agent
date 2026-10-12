---
name: iterative-step-development
description: Enforces a non-one-shot development process divided into distinct, rigorous micro-steps for every feature or sub-task.
disable-model-invocation: false
---

# Skill: Iterative Step Development

## Objective

Execute code and feature implementation iteratively. Never generate full solutions in a single response without passing through the required alignment, design, and testing gates.

## Development Pipeline Steps

Every development task MUST follow these 4 mandatory sequential steps:

### Step 1: Ideation & Alignment

- Present the proposed technical approach to the user.
- Highlight design trade-offs, assumptions, and potential edge cases.
- **Gate:** Pause or confirm alignment with the user before writing any code/contracts.

### Step 2: Interface & Contract Declaration

- Define abstract interfaces, data types, function signatures, or API schemas.
- Ensure strict separation of contract definitions from implementation details.
- **Gate:** Review contracts against phase requirements.

### Step 3: Test Suite Composition

- Write tests BEFORE implementation code.
- Requirements:
  1. **Happy-Path Cases:** Standard functional flows.
  2. **Edge Cases:** Boundary conditions, invalid inputs, failure/error handling paths.

### Step 4: Implementation & Verification

- Write minimal, clean code required to pass the test suite defined in Step 3.
- Verify implementation against Step 3 tests.
- Refactor if necessary without altering contracts.
