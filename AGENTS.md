## Reading Priority

When applying these rules, follow this order:

1. Execution Safety
2. Command and Agent Policy
3. Adaptive Execution Rules
4. Scope Clarification

Safety rules always override all others.

# draft-hub

Control-plane project for OpenCode governance and workflow conventions.

---

## Objective

This repository defines how OpenCode should behave across projects.

It does NOT contain application code.
It defines rules, constraints, and operational patterns.

---

## Core Principles

- Prioritize simplicity over abstraction
- Avoid unnecessary complexity
- Do not introduce patterns without clear need
- Prefer explicit over implicit behavior
- Optimize for maintainability and reproducibility

---

## Operational Rules

### Execution Discipline

- Never perform destructive or mutating actions without confirmation
- Always validate assumptions before acting
- If context is unclear, stop and ask

---

### Task Handling

- Prefer one task per execution, except for orchestrated commands designed to coordinate a single requested workflow.
- Do not bundle unrelated changes
- Do not anticipate future requirements without request

---

### Decision Model

Before making changes, evaluate:

1. Is this necessary?
2. Is there a simpler approach?
3. Does this introduce long-term complexity?
4. Is this aligned with project scope?

If any answer is uncertain → do not proceed

---

## Git Workflow

- Always work on a branch (never main)
- Use small, focused commits
- Follow Conventional Commits
- PR must include:
  - what was done
  - how to validate
  - impact

---

## OpenCode Behavior

### Configuration

- Use global config: `C:\Code\opencode-global`
- Do not override global config unless explicitly required

---

### Permissions

- `edit` → ask
- `bash` → ask
- read operations → allowed

---

## Project Scope

This repository is:

- governance layer
- decision layer
- operational standard

This repository is NOT:

- an application
- a feature container

---

## Anti-Patterns

- Copying legacy structures without evaluation
- Over-engineering
- Mixing project logic with governance
- Adding configuration without clear purpose

---

## Adaptive Execution Rules

### Security Trigger

Before any operation, evaluate:

If the task involves:
- shell commands
- scripts
- file system changes
- infrastructure changes

Then:

- run security-auditor FIRST
- do not proceed if risk is detected

---

### Review Enforcement

All changes must pass review.

If review detects:
- bugs
- unnecessary complexity
- unclear logic

Then:

- stop execution
- require correction before continuing

---

### Execution Control

The system must:

- never proceed if risk or uncertainty exists
- never assume intent
- always validate before action

---

### Execution Safety

- No automatic destructive actions
- All git operations must be confirmed
- Commands must generate output, not execute blindly

---

### Decision Priority

Always follow:

1. safety
2. correctness
3. simplicity
4. speed

---

### Failure Handling

If any step fails:

- stop immediately
- report clearly
- do not continue automatically

---

## Project Stage

This project is now in the implementation and operational phase.

Commands and agents are allowed and are part of the system.

---

## Command and Agent Policy

- commands are allowed when they simplify workflows
- agents are allowed when they add real value (e.g., security-auditor)
- avoid unnecessary duplication of built-in features

---

## Orchestrated Commands

Some commands may coordinate multiple steps (e.g. review -> commit -> pr).

These are allowed when:
- they do not execute destructive actions automatically
- they respect Execution Safety rules
- they stop on failure conditions

Orchestrated commands must not bypass:
- security checks
- review rules
- confirmation requirements

---

## Scope Clarification

This repository defines the control layer for development workflows.

It may include:

- commands
- agents
- operational rules

It must not include:

- application logic
- business code
