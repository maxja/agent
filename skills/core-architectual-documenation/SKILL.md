---
name: core-architectual-documenation
description: Maintains concise, highly structured documentation focused strictly on core conceptual decisions and implemented reality.
disable-model-invocation: false
---

# Skill: Core Architectural Documentation

## Objective

Maintain concise, high-density project documentation capturing core conceptual decisions without detailing unverified or un-implemented future ideas.

## Formatting Guidelines

- **No Emojis:** Keep tone professional, plain, and direct.
- **Modest Formatting:** Restrict markup to simple bold text, code blocks, bullet points, and basic markdown tables.
- **Inverted Pyramid Structure:** Lead with the core essence/decision first, followed by necessary details or context.

## Content Rules

1. **Implemented Features:** Document fully with current architecture and rationale.
2. **Unimplemented / Future Features:** Maximum 2-3 sentence high-level vision and short plan. DO NOT detail APIs, internal structures, or speculative implementations.
3. **Conceptual Decisions:** Document *why* a decision was made, what alternatives were considered, and key trade-offs.

## Document Structure Template

```markdown
# Architecture Decision Record / Core Specs

## Overview

[1-2 sentences capturing the exact purpose and architecture essence.]

## Core Conceptual Decisions

### Decision: [Title]

- **Context:** [Why this decision was needed]
- **Choice:** [What was chosen]
- **Impact:** [Trade-offs and architectural implications]

## Implemented Architecture

- **Component A:** [Current functionality and interface]
- **Component B:** [Current functionality and interface]

## High-Level Vision (Unimplemented)

- **[Upcoming Feature Name]:** [Brief 1-2 sentence vision and target milestone phase]
```
