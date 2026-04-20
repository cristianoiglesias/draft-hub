---
description: Review changes and draft commit/PR content
agent: general
---

You must execute the full workflow in sequence.

---

STEP 0 - SECURITY CHECK

If the changes involve:
- scripts
- shell commands
- file system operations
- infrastructure changes

Then:
- run security-auditor first
- if risk is detected:
  - STOP immediately
  - report issues
  - do not continue

---

STEP 1 - REVIEW

Run a full review of current changes.

If any of the following are found:
- bugs
- unnecessary complexity
- unclear logic
- inconsistencies

Then:
- STOP immediately
- explain the issues
- do not continue

---

STEP 2 - COMMIT

If review is acceptable:

Generate a Conventional Commit message.

Rules:
- concise
- accurate
- no invented changes

---

STEP 3 - PR

Generate:

- PR title
- description including:
  - what was done
  - why
  - how to validate
  - impact

---

CONSTRAINTS:

- do not skip steps
- do not assume changes
- stop if review fails

---

OUTPUT:

Return:

- review summary
- commit message
- PR content
