# Website Workspace

Dedicated workspace for the project's public-facing website.

This folder is the staging area for redesign, asset curation, and future hosting migration. It does **not** replace the current live site yet.

## Current state

- The live public site is still the Jekyll/GitHub Pages build in `docs/`.
- Existing concept assets remain in their current locations for now:
  - `background/concepts/agentic_ai_research_figma_style_design_system_board.md`
  - `figures/website-graphics-assets/`
- No existing website assets were moved as part of this scaffold. A later signed-off move plan can consolidate them here if you want.

## Structure

- `briefs/` - design prompts, concept notes, creative direction, page briefs
- `content/` - website-only copy drafts, page outlines, messaging experiments
- `figma/` - Figma handoff notes, board exports, component planning
- `assets/source/` - raw generated images, exports, and other working files
- `assets/optimized/` - web-ready versions actually intended for use in the site
- `site/` - staging area for a future rebuild that is separate from the current `docs/` deployment
- `archive/` - retired concepts and superseded website materials

## Working rule

Until a migration plan is approved, treat `docs/` as production and `website/` as the redesign sandbox.
