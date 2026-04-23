# Implementation Roadmap — Transparent Control

Living plan for the paper. Check items off as they complete; add/remove as scope evolves. Update the `last_modified` line below whenever a substantive edit is made.

**Last modified:** 2026-04-22 (appendix rebuild in Overleaf: LaTeX startup checklist + skill-protocol prose descriptions + ledger-schema tables + real sample rows + nine rules of engagement + §3.1 harness footnote + §3.3 lit-review mention + §3.3 provenance terminology fix; Stage 5b punch list added below)

---

## Stage 0 — Setup *(in progress)*

- [x] Outline drafted (`background/concepts/outline.txt`)
- [x] Project-setup protocol drafted (`project-setup.md`)
- [x] Folder structure scaffolded
- [x] `README.md`, `implementation-roadmap.md`, `asset-registry.csv`, `interaction-log.csv` created
- [x] Overleaf project located: `C:\Users\spaci\Dropbox\Apps\Overleaf\AI in the Research Process\main.tex` (working-title reconciliation pending)
- [x] Seeded `background/literature/` with HAI 2026 index, Spirling, Gordon/Samii/Su Data-NoMAD, Pepinsky (all `partially-verified`)
- [x] Candidate frontier applications drafted (`background/literature/frontier-applications.md`) — needs user selection
- [x] Adoption statistics drafted (`background/literature/adoption-statistics.md`) — needs user selection of 2–3 headline numbers
- [ ] Human-verify each literature note against primary sources *(deferred — notes stay `partially-verified` until Stage 6 review pass)*
- [x] Reconcile final title — keeping working title **"Transparent Control"** (folder name unchanged)
- [x] Sync `C:\Users\spaci\Dropbox\Skills\project-setup.md` with upgraded appendix template

## Stage 1 — Section 1: Introduction *(3 paragraphs)* — **v1 drafted**

- [x] §1.1 Motivation: drafted with Wiley 84%/25% + HAI 26-28% YoY + Pepinsky (new baseline) + S-Researcher (platform); closes on epistemic stakes
- [x] §1.2 Positioning: working manual vs. forecast; three-fold contribution (literacy / workflow / governance)
- [x] §1.3 Core principles: control + transparency, with forward reference to §4

## Stage 2 — Section 2: The AI Vocabulary — **v1 drafted**

- [x] §2.1 Fundamentals (GenAI/agentic distinction, model-instance/context window/compaction, swarms, hallucination failure modes, smart-RA metaphor)
- [x] §2.2 Key components (prompt → context → harness timeline; skills + orchestration as customization layer)
- [x] **Table 1**: 10 concepts × definitions × worked examples (already in place; \input{tables/table1-vocabulary})

## Stage 3 — Section 3: How To Deploy AI Effectively — **v1 drafted**

- [x] **Figure 1**: Setup stack (TikZ, inline) — 5-layer vertical flow with conditioning arrows
- [x] §3.1 Toolset choice (harness landscape; 3+ frontier providers; closed vs. open weights + Spirling replicability argument)
- [x] §3.2 Harness engineering (skill library + self-interview; tools & workflows; verbosity-check 3-pass discipline)
- [x] **Figure 2**: Building a skill (TikZ, inline) — trusted sources + self-interview → skill; diff-in-diff example in caption
- [x] §3.3 Context engineering (sandbox repo; orchestration + transparency artifacts; Data-NoMAD cite; project-setup skill)
- [x] **Figure 3**: Sample project setup (inline) — directory tree + workflows, two-minipage layout
- [x] §3.4 Prompt engineering (one-instance-one-task; plan-is-everything; deterministic validation)
- [x] §3.5 Agent management (stages × applications; three review disciplines — chain-of-thought, intermediate, final)
- [x] **Figure 4**: Research stages × AI (TikZ, inline) — 4-panel layout (question, theory, empirics, writing)

## Stage 4 — Section 4: Conclusions — **v1 drafted**

- [x] §4.1 Risks and ethics: direct engagement (researcher learning → control; reliability → transparency) + flagged cluster (speed/depth, discipline-level productivity gaps, environment/privacy/societal, unknown unknowns)
- [x] §4.2 Radical transparency: expanded replication package (inputs/throughputs/outputs); burden partially offset by the same infrastructure
- [x] §4.3 Flexibility & skill-building: shelf life; meta-skill of keeping up; department-level AI-readiness ask
- [x] §4.4 Future: workflow implies partial answers; positional vs. programmatic close

## Stage 4.5 — Post-drafting review (user)

- [ ] Read through v1 in Overleaf; edit prose as needed
- [ ] Resolve two editorial flags: $200/year democratizing figure in §4.1; "ChatGPT-moment" / "Claude-Code-moment" slogans in §2.2
- [ ] Confirm bib entries added by agent (esp. `sresearcher2026` author metadata) — tracked as task
- [ ] Confirm appendix renders correctly in compiled PDF (verbatim line wrapping) — tracked as task

## Stage 5 — Online Appendix — **v1 drafted**

- [x] Skill: project-setup (copied from `Skills/`, at `appendix/project-setup.md`)
- [x] Skill: skill-writing (drafted at `appendix/skill-writing.md`; synced to `Skills/skill-writing-protocol.md`)
- [x] Skill: lit-review-protocol (copied from `Skills/`, at `appendix/lit-review-protocol.md`)
- [x] Startup checklist (new at `appendix/startup-checklist.md`)
- [x] Appendix README (new at `appendix/README.md`)
- [x] Wired into `main.tex` via \verbatiminput; Replication Package pointer section added
- [ ] Replication package cleanup pass at submission time (Stage 6)

## Stage 5 — Online Appendix

- [ ] Skill-making skill (write up + source in `scripts/skills-demo/`)
- [ ] Project-setup skill (formalize `project-setup.md` as a skill)
- [ ] Full replication package = this folder, cleaned and shipped in `appendix/`

## Stage 5b — Appendix & skill-library follow-ups *(added 2026-04-22)*

- [ ] **New skill: `project-setup-existing.md`** — companion to `project-setup.md` for projects already underway. Workflow: (i) map existing folder and asset structure; (ii) propose how to implement the agentic workflow in place, offering three options — restructure the folder, add folders selectively where needed, or a minimal adoption that adds a single agent-facing folder plus the two CSV ledgers; (iii) generate a retrofit plan the user signs off on before any moves.
- [ ] **New skill: `skills-library-setup.md`** — for researchers without an existing skills library. Workflow: (i) pick a canonical library location; (ii) scaffold the folder; (iii) seed with starter skills; (iv) wire the library into the user's harness. Also usable as the "set up a new library" branch called by the connection workflow below.
- [ ] **Cross-skill workflow: connect project orchestration to the skills library.** Add to *both* `project-setup.md` and `project-setup-existing.md` a phase that (i) locates the user's skills library if present; (ii) if absent, dispatches to `skills-library-setup.md`; (iii) writes the library path into the project `README.md` under a "Skills" section so every agent instance can find it.
- [ ] **Self-interview worked example for §3.4.** Add a short appendix sidebar (or subsection) showing 5–8 actual questions the agent asked during this chapter's production when building its prompt plan, to make the prompt-level self-interview concrete. Cross-reference from §3.4 body.
- [ ] **Three review-layer checklist for §3.5.** Short three-block checklist parallel in form to the startup checklist, one block per agent-management review layer (dual chain-of-thought + final-output review; secondary validation checks; review-agent team). Add as an appendix section and cross-reference from §3.5 body.

## Stage 6 — Review & Submission

- [ ] Internal coherence pass (arguments, citations, figures)
- [ ] Verify every claim in `asset-registry.csv` to `human-verified`
- [ ] Advisor / colleague feedback round (save to `background/feedback/`)
- [ ] Final LaTeX build in Overleaf
- [ ] Submit
