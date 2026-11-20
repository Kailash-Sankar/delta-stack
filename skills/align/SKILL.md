---
name: align
description: Brainstorm a task with the user until you agree on a plan, before any work starts. Use for "let's brainstorm", "align first", "get on the same page".
disable-model-invocation: true
---

# Align

No implementation until the user approves the plan. Reading code, querying data, and small throwaway experiments are fine.

Start by restating the goal and the problem in a sentence or two, so the discussion starts in the right direction.

Then discuss, in whatever order the conversation needs:

- Ground yourself in the code, history, and data. Don't ask what you can look up, and settle by experiment what an experiment can settle. Leave product and preference calls to the user.
- Ask one question at a time, each with your recommended answer. Settle the decisions that constrain others first. Where the design is open, compare two approaches before picking one.
- Pressure-test with the lenses that matter for this task, and skip the rest: scope and non-goals, corner cases, failure modes, regressions and blast radius, testing, migration and rollout, rollback, monitoring and alerting, cost and performance.

When the open questions are settled, play back the plan: goal, done-when (a check that can pass or fail), approach, decisions and why, risks, and what's still open. Plain text for a small task; an HTML page with diagrams for a large one.

Wait for an explicit go. If the plan changes, play it back again.
