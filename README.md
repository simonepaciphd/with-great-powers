# With Great Powers — Replication Package

Companion repository for **Simone Paci**, *With Great Powers: A Practical Guide to Agentic AI for Social Science Research* (working paper, April 2026).

This repo is the full project folder used to write the paper — not a polished deliverable. It is released as a working replication package so readers can inspect the artifacts, provenance, and interaction history that the paper references.

## Quick map

| Path | What's here |
|---|---|
| [`appendix/`](appendix/) | **Online appendix** — every asset cited in the main text, including the skills dogfooded during writing (`project-setup.md`, `skill-writing.md`, `lit-review-protocol.md`, `skills-library-setup.md`, `startup-checklist.md`). |
| [`drafts/`](drafts/) | Paper drafts, including `ai-agent-draft.tex` (agent-produced first draft) and the latest compiled PDF. |
| [`background/`](background/) | Literature notes, concepts, feedback. `background/literature/` is Zotero-compatible BibTeX + per-source classification. |
| [`figures/`](figures/), [`tables/`](tables/), [`scripts/`](scripts/) | Figures, tables, and demo code referenced in the paper. |
| [`asset-registry.csv`](asset-registry.csv) | Every artifact with provenance flag (`human` / `agent` / `mixed`) and verification status. |
| [`interaction-log.csv`](interaction-log.csv) | Every non-trivial AI-assisted session from inception through final draft. |
| [`implementation-roadmap.md`](implementation-roadmap.md) | Living to-do list used during writing. |
| [`AGENTS.md`](AGENTS.md) | Rules-of-engagement for AI agents operating in this folder. Dogfoods the paper's own control/transparency principles. |

## Start here

- If you are looking for the **assets cited in the paper**, open [`appendix/`](appendix/).
- If you want to see the **workflow the paper argues for, in practice**, read [`AGENTS.md`](AGENTS.md), then browse [`interaction-log.csv`](interaction-log.csv) and [`asset-registry.csv`](asset-registry.csv) side-by-side.
- If you want to **reproduce the writing setup**, start with `appendix/project-setup.md` and `appendix/startup-checklist.md`.

## Skills

- **Library:** `C:\Users\spaci\Dropbox\Skills` (flat `.md` files).
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
