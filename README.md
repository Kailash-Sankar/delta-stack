# delta-stack

Personal agent skills for Claude Code, Codex and Cursor.

A skill here holds only the delta: what the model would not do on its own.

- Purpose first: one job per skill, named for that job.
- Don't repeat what the model already does well.
- Guide, don't constrain: no rules that push the outcome one way.
- Keep it short. Every line costs context when the skill loads.

## Layout

`skills/<name>/SKILL.md`

## Install

```
npx skills add <owner>/delta-stack --skill <name> --agent claude-code codex cursor --global --yes
```
