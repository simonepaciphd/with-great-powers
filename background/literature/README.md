# Literature — Index

## Layout

Top level:
- `README.md` — this index.
- `lit-review-strategy.md` — strand list (Phase 1 of `lit-review-protocol.md` skill).
- `lit-review-prompts.md` — **index** of per-strand prompt files and their statuses (Phase 2 meta).
- `references.bib` — consolidated BibTeX (Phase 3 output).
- `classification.csv` — per-source classification (Phase 4 output).

Subfolders (provenance split — matches asset-registry semantics):
- `ai-inputs/` — agent-authored material. Summary notes, deep-research outputs, literature suggestions that have not yet been human-verified.
  - `ai-inputs/lit-review-prompts/` — one file per strand, each holding the filled *prompt context* block (to pair with `Skills/lit-review-prompt-template.md`) and the raw agent output once received.
- `human-inputs/` — researcher-authored material. User's own notes, PDFs annotated by hand, Scholar exports, colleague recommendations, Zotero BibTeX exports.

**Agent-facing prompt template** lives at `C:\Users\spaci\Dropbox\Skills\lit-review-prompt-template.md` — it is project-agnostic and belongs in the Skills library, not in the project.

Verification rules (see `lit-review-protocol.md`):
- Everything in `ai-inputs/` starts at `partially-verified` at best.
- Material in `human-inputs/` is `human-verified` by authorship (but the upstream **source** the researcher summarized still needs independent verification if it came from the web).
- `references.bib` aggregates both; the `verification` column in `classification.csv` tracks per-source status.

## Current `ai-inputs/` contents

Stage 0 seeding (2026-04-21, all `partially-verified`):

- [`ai-inputs/hai-index-2026.md`](ai-inputs/hai-index-2026.md) — Stanford HAI 2026 AI Index
- [`ai-inputs/spirling-replicability.md`](ai-inputs/spirling-replicability.md) — Arthur Spirling on open-source LLMs
- [`ai-inputs/gordon-samii-su-data-nomad.md`](ai-inputs/gordon-samii-su-data-nomad.md) — Data-NoMAD (arXiv:2501.14651)
- [`ai-inputs/pepinsky-agentic-ai.md`](ai-inputs/pepinsky-agentic-ai.md) — Pepinsky blog Jan 2026
- [`ai-inputs/adoption-statistics.md`](ai-inputs/adoption-statistics.md) — uptake / heterogeneity cross-section (§1.1)
- [`ai-inputs/frontier-applications.md`](ai-inputs/frontier-applications.md) — candidate frontier examples (§1.1)

## To hunt next

- Munger primary source for 50% submission-increase prediction
- Wiley 2025 researcher survey primary report
- Field / career-stage adoption breakdowns
- Named APSR/AJPS/QJE papers that *used* agentic pipelines
