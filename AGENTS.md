# Transparent Control: A Practical Guide to Agentic AI for Social Science Research — Project Folder

## Project Overview

Position paper (6–8 pages) providing a practical primer on agentic AI for social science researchers. The paper argues that effective and responsible adoption rests on two governing principles — **researcher control** and **radical transparency** — and delivers a three-fold contribution: basic AI literacy, concrete workflow best practices, and governance principles for reporting.

## Project Type

position-paper

## Rules for Agents

Core rules (apply to every project):

1. **Researcher retains control.** No substantive decision (framing, argument, citation, final phrasing) is made by an agent without explicit user sign-off.
2. **One instance, one task.** Each drafting / figure / literature task starts in a fresh agent instance with a focused plan.
3. **Never modify `background/` source material.** It is read-only; derived notes or syntheses go in `drafts/` or `background/concepts/`.
4. **Register every new asset** in `asset-registry.csv` with a creator flag (`human` / `agent` / `mixed`) and verification status.
5. **Log every non-trivial session** in `interaction-log.csv`.
6. **Archive, don't delete.** Move obsolete files to the nearest `archive/` subfolder.
7. **Consult `implementation-roadmap.md`** before starting work; update it as steps complete.
8. **Skill orchestration.** Check `C:\Users\spaci\Dropbox\Skills` first. If no skill fits, ask before improvising.
9. **Validation by default.** Cross-check claims against `background/literature/`; flag any claim not traceable to a source.

Project-specific rules:

- **Citations must be traceable.** Every empirical claim (uptake statistics, benchmark citations, HAI index figures, Spirling on replicability, Gordon/Samii/Su on Data-NoMad) must be backed by a file in `background/literature/` or an explicit URL in notes. If unverifiable, mark the claim `not-verified` and flag to user.
- **The paper is itself an exemplar.** This folder doubles as the replication package for the appendix; keep it clean and fully provenance-tracked as a demonstration of the workflow the paper advocates.
- **Two dogfood skills** — *skill-making skill* and *project-setup skill* — are in scope for the online appendix. Source lives under `scripts/skills-demo/` when created.
- **No new figures fabricated from memory.** Figures 1–4 (outline) must be composed from real references or sketched and flagged `partially-verified` until reviewed.
- **Auto-commit after medium/big changes.** This repo is the replication package, so the git history is itself a deliverable. Commit and push (`origin/main`) without asking whenever you complete any of the following:
  - Advancing a stage in `implementation-roadmap.md` (or any edit that flips a stage's status).
  - Adding, renaming, or meaningfully revising any asset tracked in `asset-registry.csv` (draft sections, figures, tables, skills, literature entries).
  - Appending a non-trivial entry to `interaction-log.csv`.
  - Edits to `AGENTS.md`, `README.md`, or `.gitignore`.
  - Any change touching ≥3 files or ≥~50 lines across the working tree.

  **Do not commit** for: typo/whitespace-only tweaks, scratch edits you plan to revert in the same session, or while the user is clearly mid-edit on the same file. **Never commit** secrets, API keys, `.env` files, or anything under `.claude/`.

  **Commit style:** short imperative subject (≤70 chars) + 1–3 line body explaining the *why*. Group related edits into one commit rather than one-per-file. Push immediately after committing unless the user has said otherwise in this session.

## Folder Structure

```
AI in Social Science Research/
├── README.md                          # This file
├── project-setup.md                   # The setup protocol (template)
├── implementation-roadmap.md          # Living to-do list
├── asset-registry.csv                 # Provenance + verification
├── interaction-log.csv                # Session log
│
├── background/
│   ├── literature/                    # Cited papers, HAI index, Spirling, Data-NoMad, etc.
│   ├── concepts/                      # Outline (source-of-truth), definitions, Table 1 draft
│   ├── feedback/                      # Advisor / colleague / reviewer comments
│   └── archive/
│
├── drafts/                            # Paper drafts (Markdown / .tex)
│   └── archive/
│
├── figures/                           # Figures 1–4 (final + sources)
│   └── archive/
│
├── tables/                            # Table 1 (concepts & definitions)
│   └── archive/
│
├── scripts/                           # Demo skills + any code for the paper
│   └── archive/
│
└── appendix/                          # Online appendix replication package
    └── archive/
```

## Implementation Roadmap

See `implementation-roadmap.md`.

## Asset Registry

See `asset-registry.csv`. Schema documented in `project-setup.md`.

## Interaction Log

See `interaction-log.csv`. Schema documented in `project-setup.md`.

## Language & Tools

- **Primary writing:** Markdown (drafting), LaTeX (final typesetting via Overleaf).
- **Code (demos / figures):** Python or R as needed; kept minimal.
- **References:** BibTeX in `background/literature/`.

## Skills

- Skill library: `C:\Users\spaci\Dropbox\Skills`
- Relevant existing skills: `paper-writing-protocol.md`, `project-setup.md`.
- Candidate new skills (for appendix): *skill-making skill*, *project-setup skill* (this protocol, hardened).

## Overleaf Integration

- Overleaf root: `C:\Users\spaci\Dropbox\Apps\Overleaf`
- **This paper's Overleaf project:** `C:\Users\spaci\Dropbox\Apps\Overleaf\AI in the Research Process\main.tex` (author: Simone Paci, April 2026; currently a bare scaffold).
- Note: the Overleaf title ("AI in the Research Process") may diverge from the working title in this README ("Transparent Control…") — confirm which is the final title before submission.
