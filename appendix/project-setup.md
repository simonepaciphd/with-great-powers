# Project Setup Protocol

This file is both a **template** and a **setup instruction** for agentic AI tools working in a social science research project. Copy it into a new project folder and either (a) fill in the bracketed placeholders manually and rename to `README.md`, or (b) invoke an agent with "run the project-setup protocol" to scaffold the folder semi-automatically.

The protocol reflects two governing principles from *With Great Powers* (working paper): **researcher control** (humans retain all key decisions) and **radical transparency** (full provenance and verification tracking for every asset).

---

## How to Use (Agent Instructions)

When asked to run this protocol, an agent should:

1. Ask the user for the **project title**, **project type** (empirical-research | position-paper | literature-review | data-exploration | methodological | other), and any **project-specific rules**.
2. Create the folder structure under the "Folder Structure" section below, pruning branches that do not apply (e.g., a pure writing project can omit `inputs/`, `outputs/`, `scripts/`).
3. Generate a filled-in `README.md` from the template section below.
4. Generate `implementation-roadmap.md` by translating the user's outline / plan into a checkable to-do list.
5. Generate `asset-registry.csv` and `interaction-log.csv` with the schemas specified below. Pre-populate the registry with any files already present in the folder.
6. Report the final structure back to the user and confirm before proceeding to substantive work.

---

# [Project Title] — Project Folder

## Project Overview

[1–3 sentences: research question / purpose, approach, and expected output (paper, replication package, dataset, memo).]

## Project Type

[empirical-research | position-paper | literature-review | data-exploration | methodological | other]

## Rules for Agents

Core rules (apply to every project):

1. **Researcher retains control.** No substantive decision (design, interpretation, final phrasing, model/method choice) is made by an agent without explicit user sign-off.
2. **One instance, one task.** Start each non-trivial task in a fresh agent instance with a focused plan. Do not accumulate unrelated threads in a single context.
3. **Never modify files in `inputs/`** (empirical projects) or `background/` source material. These are read-only; derived artifacts go elsewhere.
4. **Register every new asset** (draft, figure, table, script, dataset, note) in `asset-registry.csv` with a creator flag (`human` / `agent` / `mixed`) and verification status (`not-verified` / `partially-verified` / `human-verified`).
5. **Log every non-trivial session** in `interaction-log.csv` with date, input/output summary, and model metadata.
6. **Archive, don't delete.** Move obsolete files to the nearest `archive/` subfolder.
7. **Consult `implementation-roadmap.md`** before starting work and update it as steps complete.
8. **Skill orchestration.** For any complex task, first check the skill library at `C:\Users\spaci\Dropbox\Skills`. If no skill fits, ask the user whether to create one before improvising.
9. **Validation by default.** Prefer deterministic validation checks (tests, reproducibility runs, cross-source comparisons) over self-assessment.

Project-specific rules:

[Add constraints specific to this project — e.g., "all figures reproducible from scripts in figures/", "never cite sources outside background/literature/", "freeze section X after advisor review."]

## Folder Structure

Full template (prune branches that do not apply):

```
Project Folder/
├── README.md                      # This file, filled in
├── implementation-roadmap.md      # Living to-do list / plan
├── asset-registry.csv             # Provenance + verification tracking
├── interaction-log.csv            # Session-level user-agent log
│
├── background/                    # Project knowledge (read-only source material)
│   ├── literature/                # Papers, references
│   ├── concepts/                  # Definitions, frameworks, notes
│   ├── feedback/                  # Advisor / reviewer / colleague notes
│   └── archive/
│
├── drafts/                        # Paper / memo drafts (writing projects)
│   └── archive/
│
├── figures/                       # Final figures (+ source if reproducible)
│   └── archive/
│
├── tables/                        # Final tables
│   └── archive/
│
├── scripts/                       # All code (empirical or demo)
│   ├── data-collection/
│   ├── data-cleaning/
│   ├── data-management/
│   ├── data-analysis/
│   └── archive/
│
├── inputs/                        # Raw & cleaned data — READ-ONLY at raw level
│   ├── raw/
│   ├── clean/
│   └── archive/
│
├── outputs/                       # Generated analysis results
│   ├── results/
│   └── archive/
│
└── appendix/                      # Replication package shipped with final output
    └── archive/
```

Guidance:
- **Writing-only projects** (position papers, literature reviews): keep `background/`, `drafts/`, `figures/`, `tables/`, optionally `scripts/` (for demos) and `appendix/`. Omit `inputs/` and `outputs/`.
- **Empirical projects**: keep the full tree. The data pipeline (raw → clean → merged → results) runs through `scripts/` and `inputs/` → `outputs/`.
- **Every subfolder** has a sibling `archive/` for routine cleanup.

## Implementation Roadmap

See `implementation-roadmap.md` — the living plan for this project. Agents read it before starting work and check off items as they complete. Material changes to scope or sequencing must be confirmed with the user.

## Asset Registry

Every major asset is tracked in `asset-registry.csv`. Schema:

| Column | Values |
|--------|--------|
| `asset_path` | Relative path from project root |
| `asset_type` | draft \| figure \| table \| script \| dataset \| note \| reference \| other |
| `creator` | human \| agent \| mixed |
| `model_metadata` | Model ID + harness (e.g., `claude-opus-4-7 / claude-code`); blank if `human` |
| `created` | YYYY-MM-DD |
| `last_modified` | YYYY-MM-DD |
| `verification` | not-verified \| partially-verified \| human-verified |
| `notes` | Free text (purpose, known issues, review status) |

Agents must append a row when creating a new asset and update `last_modified` + `verification` on substantive edits.

## Interaction Log

Every non-trivial user-agent session is logged in `interaction-log.csv`. Schema:

| Column | Values |
|--------|--------|
| `date` | YYYY-MM-DD |
| `session_id` | Short identifier (e.g., `2026-04-21-a`) |
| `harness` | claude-code \| chatgpt \| codex \| antigravity \| other |
| `model` | Model ID (e.g., `claude-opus-4-7`) |
| `researcher_input_summary` | 1–2 sentences |
| `agent_output_summary` | 1–2 sentences |
| `assets_affected` | Comma-separated paths (match `asset-registry.csv`) |
| `notes` | Free text |

Optional: for reproducibility-critical projects, consider cryptographic attestation of log entries (see Gordon, Samii, Su — Data-NoMad, arxiv).

## Data Sources *(empirical projects only)*

| Source | File(s) | Coverage |
|--------|---------|----------|
| [Dataset name] | `inputs/raw/[filename]` | [Years / waves / scope] |

## Cleaned Data *(empirical projects only)*

All cleaned data lives in `inputs/clean/` as [format] files, following the naming convention `[convention]`.

## Analysis Pipeline *(empirical projects only)*

1. **Raw data** → `scripts/data-cleaning/` → **Cleaned data** (`inputs/clean/`)
2. **Cleaned data** → `scripts/data-management/` → **Merged analysis-ready data**
3. **Merged data** → `scripts/data-analysis/` → **Results** (`outputs/results/`)

## Key Methodological Notes *(empirical projects only)*

- **Dependent variable(s):** [...]
- **Independent variable(s):** [...]
- **Method:** [...]

## Language & Tools

- **Primary language(s):** [e.g., R, Python, Stata, LaTeX]
- **Raw data formats:** [.csv, .sav, .dta, .rds, ...]
- **Output formats:** [.parquet, .rds, .pdf, ...]

## Skills

- Skill library: `C:\Users\spaci\Dropbox\Skills`
- For any complex task, check for an appropriate skill first. If none fits, ask the user whether to create one before improvising.

## Overleaf Integration

- Overleaf root: `C:\Users\spaci\Dropbox\Apps\Overleaf`
- Ask whether an Overleaf project already exists for this work and whether to set one up / link it.
