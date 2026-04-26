---
name: skill-writing
description: Drafts or revises a local workshop skill from one anchor source plus the participant's own recurring practice. In this package it is usually used to revise or rebuild skills/operationalize.md.
---

# /skill-writing - build a reusable workshop skill

This skill powers the live "skill build" demo. In this package, the default use case is to revise or rebuild `skills/operationalize.md` from the local Adcock and Collier source plus the participant's own judgment about how measurement decisions should be made.

## When to use

- A recurring workshop task needs a reusable local playbook.
- The participant wants to revise `skills/operationalize.md` rather than rely on the shipped version untouched.
- A local skill is close to right but needs the participant's own rules and anti-patterns written down.

## Do not use when

- The task is one-off and does not deserve a reusable playbook.
- The participant has not formed a view about how the task should be done yet.
- The goal is to install a full external skills library. This package is deliberately local.

## The interview

1. **Confirm the target skill.** Default to `skills/operationalize.md` unless the participant names another local skill.
2. **Decide whether to revise or rebuild.** If the target file already exists, ask whether to update it in place or create a clearly named variant.
3. **Extract the recurring task.** Ask what the skill should help the agent do every time, not just today.
4. **Extract the judgment calls.** Ask for the recurring decisions, the anti-patterns to avoid, and what a good output must contain.
5. **Read the local anchor source.** In this package, the default source is `skills/sources/Adcock and Collier 2001 apsr - measurement validity in social sciences.pdf`.
6. **Match the house style.** Use the same structure as the neighboring local skills: YAML frontmatter plus `When to use`, `Do not use when`, `The interview`, `Failure modes`, `Output`, `Handoff`, and `Explicit non-claims`.
7. **Revise or draft the file.** If the target already exists, revise in place and explicitly summarize what changed.

## Failure modes

- **Generic textbook prose.** The skill reads like a methods summary rather than the participant's preferred procedure. Keep the participant's choices load-bearing.
- **Silent overwrite.** The agent rewrites an existing local skill without confirming whether the participant wants revision or a variant.
- **Dropped anti-patterns.** The draft explains what to do but not what to watch out for. Include concrete failure modes.
- **External dependency creep.** The draft assumes a global skill library, persona stack, or memory stack. Keep the skill package-local.

## Output

Produce or revise one local skill file in `skills/` with:

- YAML frontmatter containing `name` and `description`
- a clearly named procedure the participant can invoke again
- explicit failure modes
- explicit non-claims

## Handoff

After `/skill-writing`, use the revised skill immediately in the workflow. In this package that usually means moving from `/skill-writing` straight to `/operationalize`.

## Explicit non-claims

This skill does not decide the participant's preferred method on its own. It encodes the participant's view into a reusable local playbook.
