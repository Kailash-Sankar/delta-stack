---
name: explain
description: Explain how a part of the codebase works and why it is built that way. Use for "how does X work", "why is X like this", "where should this live", or understanding an area before changing it.
disable-model-invocation: true
---

# Explain

"How" is answered from the code. "Why" is answered from the record. Many questions need both.

Write plainly. When the answer is a flow, a sequence, or a structure, draw it: ASCII in a terminal, Mermaid where it renders. Make an HTML page only when the explanation has many parts or will be shared; keep it to about two printed pages, diagrams first, and cut detail before cutting a diagram.

## How

Explore in a subagent so the main thread keeps only the explanation. Aim for a mental model a senior engineer new to the area could work from: entry points, how data and control flow, where state lives, which boundaries matter, and where a change would go.

## Why

Don't infer intent from the code's shape. Read the record:

- `git log -S` / `git log -L` / blame on the lines in question, back to the commit that introduced them
- the PRs behind those commits, including review comments, and the issues they link
- design docs, ADRs, and incident notes if the trail points there

Quote or cite what the authors wrote (commit, PR #, issue). Label your own inferences as inferences. Say what the record does not answer.
