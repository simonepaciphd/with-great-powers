# Startup Checklist: From Chat to Harness

For researchers already using chat-mode AI who are setting up their first agentic project. Each item is one action. The five sections map onto the setup stack of the *Transparent Control* paper (\S3).

## Tool

- [ ] Install one harness (Claude Code, Codex, Antigravity, Cursor, or equivalent). Learn one before comparing.
- [ ] Authenticate and run a trivial read / write / execute test.

## Harness

- [ ] Copy one existing skill from your skill library. Do not start from scratch.
- [ ] Wire one deterministic validation check into the workflow: a type check, a reference count, a schema validation, a unit test.

## Context

- [ ] Scaffold a project folder with the `project-setup.md` protocol.
- [ ] Populate `background/` with your papers, data, and prior drafts.
- [ ] Initialize `asset-registry.csv` and `interaction-log.csv` and commit to using them from the first session.

## Prompt

- [ ] Start a fresh instance scoped to one task.
- [ ] Write the plan before the agent runs. The plan is the substantive work.
- [ ] Run the validation check at the end, not the agent's self-report.

## Agent management

- [ ] Inspect the agent's chain of thought, not only its final output.
- [ ] Sign off explicitly before committing any agent-produced artifact.
- [ ] Log the session in `interaction-log.csv` before closing the instance.

## Before the next project

- [ ] Note the skill gaps this project surfaced. Draft the missing skills with `skill-writing.md` before the next deadline.
- [ ] Archive obsolete files. Do not delete.

---

*Next: \S2 for vocabulary, \S3 for the full workflow, \S4 for the risks and governance this checklist implements in miniature.*
