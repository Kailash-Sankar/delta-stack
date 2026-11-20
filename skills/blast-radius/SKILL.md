---
name: blast-radius
description: Find what a change could break outside its diff, and prove the fact its safety rests on. Use for "blast radius", "what could this break", or a diff you don't trust yet.
disable-model-invocation: true
---

# Blast radius

Listing callers is not the job; grep does that. Look for breakage a symbol search misses:

- Data that crosses a boundary: API responses, DB columns, queues, files, wire formats, another language or service reading the same bytes.
- Indirect wiring: config, feature flags, env vars, string-keyed lookups, reflection, generated code.
- Timing and lifecycle: init order, teardown, retries, concurrency, caching.
- The library's real behavior at the pinned version (and any local patch), not what its docs or your memory say.

## Find the one fact

A change that looks risky is usually safe because of one fact ("this only drops entries that are already dead"). Find it. If it holds, most risks clear at once. Spend the effort here, not on a long list of maybes.

Then prove it as far as is cheap, and say where you stopped:

1. Asserted
2. Pointed at the code (`file:line`, or the library source)
3. Walked the failure path and showed it can't be reached
4. Ran real code: a script or test that calls the actual function and fails loudly if you're wrong
5. Reproduced in the running system

Some facts can't be run here: prod data, deploy config, external services. Stop at the highest level you can reach and mark the fact unproven. Don't write it up as if you had checked it.

## Report

- **Change:** what it does differently, including what the diff doesn't spell out
- **Safety fact:** the fact, its proof level, the evidence
- **Risks:** how it breaks, where, how likely, how bad
- **Cleared:** what you checked and why it's fine
- **Before merge:** the cheapest test or repro that would catch the real bug
