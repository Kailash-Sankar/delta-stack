# delta-stack

Personal skills for coding agents, in the Agent Skills format.

A skill here holds only the delta: what the model would not do on its own.

- Purpose first: one job per skill, named for that job.
- Don't repeat what the model already does well.
- Guide, don't constrain: no rules that push the outcome one way.
- Keep it short. Every line costs context when the skill loads.

## Layout

`skills/<name>/SKILL.md`

## Install

```
npx skills add Kailash-Sankar/delta-stack --skill <name> --agent <agent...> --global --yes
```
