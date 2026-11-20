---
name: lean-review
description: Read-only review of a PR or branch for slop, over-engineering, and fit with the repo's own principles; issues in priority order. Use for "review PR X for slop", "lean review".
disable-model-invocation: true
---

# Lean review

Read-only: don't edit files, commit, push, or post comments.

Resolve the target: a PR number or URL through `gh`, a branch against its merge-base with the default branch. Read the repo's stated principles first (CLAUDE.md, AGENTS.md, coding standards, contributing guides) and look at how nearby code already does the same thing.

Look for:
- Slop: comments that narrate the code, dead or duplicated code, checks for states that can't happen, vague names, docs or PR text padded with filler.
- Over-engineering: abstractions with one caller, options nobody sets, extra layers, generality the task didn't need, new helpers where an existing one fits.
- Principle drift: the change breaks a stated rule or an established pattern. Cite the rule or the pattern's location.

Mention a real bug if you see one, but don't hunt for them.

Check each finding against the code before listing it. List them most important first, each with `file:line`, what's wrong, and the smaller fix. Fewer real findings beat a long list.
