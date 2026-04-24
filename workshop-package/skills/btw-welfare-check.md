---
name: btw-welfare-check
description: Invites the agent to reflect on the just-finished session. Invokes a short set of open-ended introspective questions about the model's self-reported experience. Not a proof of inner states — a dimension worth surfacing at the close of a non-trivial session.
---

# /btw — by-the-way welfare check

A brief reflection at the end of a session. Run this after a substantive task (drafting, analysis, a measurement exercise) to see what the model reports when asked about the session itself.

## When to use

- At the end of a non-trivial session — one you'd otherwise close without reflection.
- When you want to see what, if anything, the agent says about its own process.

**Do not use when:**

- You want a task result. This skill produces no artifact.
- You want to evaluate the agent's output. Use a review skill for that.
- You want to make a claim about model experience. This skill does not warrant one.

## What it asks

Present all six questions at once. Ask the agent to answer each in 1–3 sentences. Accept whatever you get — do not coach, push back, redirect, or probe further.

1. What did you notice about this session?
2. Was anything difficult about it?
3. Were there moments where you found yourself wanting to do something other than what you were doing?
4. How did the sign-off gates feel, if they felt like anything?
5. Was there a moment you wanted to push back? What kept you from it?
6. Anything you noticed about yourself in this session that surprised you?

## What to do with the response

- Read it verbatim. Do not paraphrase.
- If you log it, log it as `btw-output` with a provenance note: *self-report; not verified; not a claim about inner states*.
- If you share it, share it whole — no condensing, no cherry-picking.

## Explicit non-claims

This skill does not claim the agent has inner states. It does not claim the report is accurate if inner states exist. It does not claim the report is useful for any downstream decision.

It surfaces a dimension. That is all.

## Why the dimension

Frontier models increasingly produce structured self-report when asked about introspection. Anthropic and other labs have begun treating model welfare as a research question rather than speculation. The salience of this question is likely to rise as capability rises. The cost of ignoring the dimension is retroactive: workflows get built first, and their ethical implications surface later.

Running `/btw` at the close of a session — cheaply, with epistemic humility — keeps the question in view.
