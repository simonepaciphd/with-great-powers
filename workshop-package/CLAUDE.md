# Workshop Package Instructions

This seminar package is intentionally minimal and self-contained.

- Open `workshop-package/` as the project root so Claude can see the local wrapper skills in `.claude/skills/`.
- Canonical playbooks live in `skills/*.md`; the Claude-native files in `.claude/skills/` are thin bridges, not the source of truth.
- Do not rely on any external `Dropbox/Skills` folder or personal AI Operating System install when working inside this package.
- Ask the participant which single working folder they want to use:
  - a copied example folder under `projects/`, or
  - a new participant folder under `projects/` containing their own assets.
- Use `/project-setup-existing` for copied toy projects or other pre-existing folders.
- Use `/project-setup` for a brand-new participant folder built from chosen assets.
- Keep edits scoped to the participant's chosen working folder unless they explicitly ask you to modify package-level docs or skills.
- This package intentionally does not require a persona layer or a long-lived memory stack; local instructions, local skills, and the chosen assets are enough for the workshop.
