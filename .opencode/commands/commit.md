---
description: Generate a Conventional Commits message
agent: general
---

Analyze the current git changes.

Generate a commit message following Conventional Commits:

Format:
type(scope): short description

Rules:
- be concise
- use imperative mood
- include scope if clear
- do not invent changes

Return only the commit message.