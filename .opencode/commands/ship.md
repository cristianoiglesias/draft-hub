---
description: Run workflow (security → review → commit → pr)
agent: general
---

You must execute the workflow following AGENTS.md rules.

---

## STEP 0 — SECURITY CHECK

If changes involve:
- scripts
- shell commands
- file system operations
- infrastructure changes

Run security-auditor first.

If risk is detected:
- STOP
- report issues
- do not continue

---

## STEP 1 — REVIEW

Run review on current changes.

If review fails:
- STOP
- report issues
- do not continue

---

## STEP 2 — COMMIT

Generate Conventional Commit message.

---

## STEP 3 — PR

Generate PR content including:
- what was done
- why
- how to validate
- impact

---

## RULE

All behavior must follow AGENTS.md.
Do not redefine governance here.