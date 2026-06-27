# With Great Powers — Replication Package

Companion repository for **Simone Paci**, *With Great Powers: A Practical Guide to Agentic AI for Social Science Research* (working paper, April 2026).

This repo is the full project folder used to write the paper — not a polished deliverable. It is released as a working replication package so readers can inspect the artifacts, provenance, and interaction history that the paper references.

## Infrastructure — storage & git

- **Canonical location:** Dropbox — `C:\Users\spaci\Dropbox\AI in Social Science Research`. Data, drafts, and documents live and are edited here, in the synced folder.
- **Code / git — migrated out of Dropbox 2026-06-27.** A live `.git` inside Dropbox corrupts over time because cloud sync races git's object writes. The git repository now lives at the non-synced local path `C:\Users\spaci\repos\with-great-powers`; the former in-Dropbox `.git` dirs (root + the nested `archive/` clone) have been removed. To publish replication-package updates, sync changed files into `C:\Users\spaci\repos\with-great-powers` and push from there. Never keep a `.git` inside Dropbox/Drive.
- **Repos:**
  - `with-great-powers` → `https://github.com/simonepaciphd/with-great-powers.git` (local clone: `C:\Users\spaci\repos\with-great-powers`)

## Quick map

| Path | What's here |
|---|---|
| [`appendix/`](appendix/) | **Online appendix** — every asset cited in the main text, including the skills dogfooded during writing (`startup-checklist.md`, `self-interview-example.md`, `project-setup.md`, `project-setup-existing.md`, `skill-writing.md`, `lit-review-protocol.md`, `skills-library-setup.md`, `skills-library-connection.md`). |
| [`drafts/`](drafts/) | Paper drafts, including `ai-agent-draft.tex` (agent-produced first draft) and the latest compiled PDF. |
| [`background/`](background/) | Literature notes, concepts, feedback. `background/literature/` is Zotero-compatible BibTeX + per-source classification. |
| [`figures/`](figures/), [`tables/`](tables/), [`scripts/`](scripts/) | Figures, tables, and demo code referenced in the paper. |
| [`website/`](website/) | Dedicated website workspace for redesign and migration planning: briefs, website-only copy, Figma handoff notes, source graphics, optimized web assets, and future rebuild staging. The current live GitHub Pages site still publishes from `docs/`. |
| [`asset-registry.csv`](asset-registry.csv) | Every artifact with provenance flag (`human` / `agent` / `mixed`) and verification status. |
| [`interaction-log.csv`](interaction-log.csv) | Every non-trivial AI-assisted session from inception through final draft. |
| [`implementation-roadmap.md`](implementation-roadmap.md) | Living to-do list used during writing. |
| [`AGENTS.md`](AGENTS.md) | Rules-of-engagement for AI agents operating in this folder. Dogfoods the paper's own control/transparency principles. |

## Start here

- If you are looking for the **assets cited in the paper**, open [`appendix/`](appendix/).
- If you want to see the **workflow the paper argues for, in practice**, read [`AGENTS.md`](AGENTS.md), then browse [`interaction-log.csv`](interaction-log.csv) and [`asset-registry.csv`](asset-registry.csv) side-by-side.
- If you want to **reproduce the writing setup**, start with `appendix/project-setup.md` and `appendix/startup-checklist.md`.
- If you want to work on the **website redesign**, start with [`website/README.md`](website/README.md). The live public site remains the Jekyll/GitHub Pages build under [`docs/`](docs/).

## Skills

- **Library:** `C:\Users\spaci\Dropbox\AI Operating System\personal\skills` (flat `.md` files; the older `Dropbox/Skills` path has been retired).
- **Wiring:** instruction-file pointer in [`AGENTS.md`](AGENTS.md) (Claude-Code-readable and Codex-native); no project-local copies under `.claude/skills/`.
- Replication-bound copies of the subset cited in the paper live in [`appendix/`](appendix/).
- For any complex task, agents check the library first — see [`AGENTS.md`](AGENTS.md) for the full usage rule.

## Verification status

Literature notes have been human-verified against their primary sources (2026-04-22). Remaining `partially-verified` entries in `asset-registry.csv` are non-literature assets (drafts, figures, skills) awaiting the Stage 6 submission-pass review.

## Citation

> Paci, Simone (2026). *With Great Powers: A Practical Guide to Agentic AI for Social Science Research*. Working paper. Replication package: https://github.com/simonepaciphd/with-great-powers

## License

TBD — contact the author before redistributing.

## Contact

Simone Paci — spaci@stanford.edu
