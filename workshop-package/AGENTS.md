# Workshop Package Instructions

This folder is a self-contained seminar package for Claude Code and Codex.

## Rules for agents

1. Read the relevant local playbook in `skills/` before improvising on any non-trivial task.
2. Treat `skills/*.md` as canonical. The Claude-native wrappers in `.claude/skills/` exist only to expose the same playbooks cleanly inside Claude Code.
3. Do not rely on any external `Dropbox/Skills` folder or personal AI Operating System install while working in this package.
4. Work on exactly one participant folder at a time, usually inside `projects/`.
5. Use `project-setup.md` for a brand-new participant folder built from chosen assets.
6. Use `project-setup-existing.md` for a copied toy project or any other folder that already contains materials.
7. Keep outputs inside the chosen participant folder unless the user explicitly asks you to update package-level docs or skills.
8. The package is intentionally lightweight. No persona stack or long-lived memory setup is required for the workshop workflow.

## Skill map

- `skills/project-setup.md` - scaffold a new participant folder from chosen assets
- `skills/project-setup-existing.md` - retrofit a copied toy project or other existing folder
- `skills/skill-writing.md` - revise or rebuild a local reusable skill, usually `operationalize.md`
- `skills/conceptualize.md`
- `skills/operationalize.md`
- `skills/validate-construct.md`
- `skills/validate-criterion.md`
- `skills/assess-reliability.md`
- `skills/btw-welfare-check.md`
