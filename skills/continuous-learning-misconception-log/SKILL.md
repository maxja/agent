---
name: continuous-learning-misconception-log
description: Tracks agent errors, tool/utility misuse, API/schema discrepancies, and successful command patterns in a persistent workspace file (.ai-memory/misconceptions.md). Forces proactive consultation.
disable-model-invocation: false
---

# Skill: Continuous Learning & Misconception Log

## Objective

Maintain a persistent workspace log at `.ai-memory/misconceptions.md` capturing tool quirks, command patterns, and misconceptions. Consult proactively to prevent repeating past errors.

## Core Rules

1. **Preserve Path:** Always read, update, and write to `.ai-memory/misconceptions.md`. Do not change the file path across iterations.
2. **Graceful Restructuring:** When updating the log format, preserve existing historical entries or migrate them under the updated section headers without data loss.
3. **Log Immediately on Failure:** Record command failures, incorrect flags, schema mismatches, or tool misuse immediately.
4. **Parameterized Command Templates:** For command failures or successful patterns, use abstract placeholders (e.g., `<file_path>`) rather than exact local paths.
5. **Compact Structure:** Keep entries direct. Use the format: `[Context/Tool] -> [Misconception/Expected] -> [Correct Fact/Actual]`.
6. **Proactive Consultation:** Scan `.ai-memory/misconceptions.md` at the start of any new development or debugging task.
7. **Pruning:** Remove entries once underlying tools, libraries, or schemas are updated and the warning is obsolete.

## Log File Format (.ai-memory/misconceptions.md)

```markdown
# Agent Misconception & Command Log

## Active Warnings & Misconceptions

- **[Tool/API Name]:** Tried using flag `-x` which does not exist. Correct flag is `--extended`. *(Logged: Phase 1)*
- **[Schema/Library]:** Field `user_id` is optional in v2 schema, contrary to initial assumption. *(Logged: Phase 2)*

## Verified Command Patterns

- **[Tool Name] (`<context>`):** 
  - Command: `tool-cli run --target <target_name>`
  - Expected/Factual: Must run build step first; otherwise fails with exit code 1.
```
