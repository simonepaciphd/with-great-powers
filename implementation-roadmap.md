# Implementation Roadmap — With Great Powers

Living plan for the paper. Check items off as they complete; add/remove as scope evolves. Update the `last_modified` line below whenever a substantive edit is made.

**Last modified:** 2026-05-05 (May 18 departmental workshop scoped: 90-min "methods lunch" workshop announced for 2026-05-18, 12-1:30pm. Builds on the existing 1h seminar but more practical, no participant code-along (Simone demos live), and ships a redistributable AI OS install package in three modular tiers. Decisions logged: (1) scaffolding-only sanitization across tiers; (2) Claude Code + Codex only, no Antigravity in v1; (3) single linear track with optional sidebars for the diverse audience; (4) new deck authored in the Overleaf project at `C:\Users\spaci\Dropbox\Apps\Overleaf\AI in the Research Process\`; (5) `docs/seminar.md` lightly rewritten as evergreen, no May-18 mention; (6) solo build. New parallel track added below. Previously 2026-04-26 (Parallel website track initialized: `website/` workspace scaffolded for redesign/migration planning without moving the live `docs/` site or the existing concept assets under `figures/website-graphics-assets`; top-level README updated to document the split. Workshop package hardened the same day: added package-local `CLAUDE.md` / `AGENTS.md`, Claude-native wrapper skills under `workshop-package/.claude/skills/`, workshop-specific `project-setup` and `project-setup-existing` skills, and participant guidance for creating one working folder from either a copied toy project or participant-supplied assets. Previously 2026-04-23 (Stage 4.5 editorial pass partially closed by user — $200/year figure removed from §4.1, "ChatGPT moment" slogan kept in §2.2, v1 read-through done; Stage 5b #4 drafted — self-interview worked example on survey-questionnaire design added as \S B of online appendix, cross-referenced from §3.4; Stage 5b #5 three-review-layer checklist dropped from scope per user decision. Previously 2026-04-23 (Stage 0 literature-verification closed; Stage 5b #1 project-setup-existing.md drafted; #2 skills-library-setup.md closed out with Phase 2.5 + dogfood pass; #3 skills-library-connection.md drafted and run live on this project). Previously 2026-04-22 (title changed from "Transparent Control" to "With Great Powers: A Practical Guide to Agentic AI for Social Science Research"; appendix rebuild in Overleaf).

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
- [x] Human-verify each literature note against primary sources *(completed 2026-04-22; all lit notes reviewed against primary sources by user)*
- [x] Reconcile final title — initial decision (2026-04-21) was to keep **"Transparent Control"**; title changed (2026-04-22) to **"With Great Powers: A Practical Guide to Agentic AI for Social Science Research"** (folder name unchanged)
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

- [x] Read through v1 in Overleaf; edit prose as needed *(done 2026-04-23)*
- [x] Resolve two editorial flags: $200/year figure removed from §4.1; "ChatGPT moment" / "Claude-Code moment" slogans kept in §2.2 *(done 2026-04-23)*
- [ ] Confirm bib entries added by agent (esp. `sresearcher2026` author metadata) — tracked as task, bumped to Stage 6
- [ ] Confirm appendix renders correctly in compiled PDF — tracked as task, bumped to Stage 6

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

- [x] **New skill: `project-setup-existing.md`** — companion to `project-setup.md` for projects already underway. Workflow: (i) map existing folder and asset structure; (ii) propose how to implement the agentic workflow in place, offering three options — restructure the folder, add folders selectively where needed, or a minimal adoption that adds a single agent-facing folder plus the two CSV ledgers; (iii) generate a retrofit plan the user signs off on before any moves. *(Drafted 2026-04-23 at `Skills/project-setup-existing.md` and `appendix/project-setup-existing.md`; appendix README updated. Not yet dogfooded.)*
- [x] **New skill: `skills-library-setup.md`** — for researchers without an existing skills library. Workflow: (i) pick a canonical library location; (ii) scaffold the folder; (iii) seed with starter skills; (iv) wire the library into the user's harness. Also usable as the "set up a new library" branch called by the connection workflow below. *(Drafted 2026-04-22 at `appendix/skills-library-setup.md`; synced to canonical `Skills/` library 2026-04-23; Phase 2.5 added 2026-04-23 for retroactive flat→native format wrapping when a harness-native librarian pattern is chosen on an existing flat library. Dogfooded 2026-04-23 via the connection skill run on this project.)*
- [x] **Cross-skill workflow: connect project orchestration to the skills library.** Add to *both* `project-setup.md` and `project-setup-existing.md` a phase that (i) locates the user's skills library if present; (ii) if absent, dispatches to `skills-library-setup.md`; (iii) writes the library path into the project `README.md` under a "Skills" section so every agent instance can find it. *(Drafted 2026-04-23 as a standalone skill `skills-library-connection.md` rather than inline phases, so the wiring is harness-adaptive — Claude Code / Codex / Cursor each get a different lowest-friction default based on the library format (flat `.md` vs. SKILL.md-directory native). Both `project-setup.md` variants now dispatch to it. Also synced `skills-library-setup.md` from appendix into the canonical `Skills/` library so the handoff works for other projects.)*
- [x] **Self-interview worked example for §3.4.** *(Drafted 2026-04-23 as \S B of the online appendix, `appendix/self-interview-example.md` + Overleaf mirror. Didactic illustration on survey-questionnaire design with 8 Q&A pairs under a load-bearing + domain-dominant selection rubric; scope pivoted from "questions asked during this chapter's production" to a generic social-science instrument at user's direction. Cross-referenced from §3.4 body; appendix intro updated from "four complementary artifacts" to "five".)*
- [ ] ~~**Three review-layer checklist for §3.5.**~~ *Dropped from scope 2026-04-23 per user decision.*

## Parallel track — Website companion

- [x] Scaffold `website/` workspace with dedicated subfolders for briefs, website-only copy, Figma notes, source graphics, optimized web assets, rebuild staging, and archive *(done 2026-04-26)*
- [x] Preserve current deployment path: live public site stays under `docs/` / GitHub Pages while redesign work accumulates under `website/` *(confirmed 2026-04-26)*
- [ ] Decide, in a separate signed-off move plan, whether to migrate `background/concepts/agentic_ai_research_figma_style_design_system_board.md` and `figures/website-graphics-assets/` into `website/`
- [ ] Rebuild the website for production hosting (Hostinger or other target) — separate task

## Parallel track — Seminar package

- [x] Add package-local `workshop-package/CLAUDE.md`, `workshop-package/AGENTS.md`, and Claude-native wrapper skills under `workshop-package/.claude/skills/` so the seminar ZIP is self-contained for Claude Code and Codex *(done 2026-04-26)*
- [x] Add workshop-specific `project-setup.md`, `project-setup-existing.md`, and `skill-writing.md` to support both copied toy projects and participant-created folders *(done 2026-04-26)*
- [x] Clarify participant setup: create one working folder under `workshop-package/projects/` from either a copied example or participant-supplied assets *(done 2026-04-26)*
- [ ] Keep `docs/seminar.md`, `workshop-package/participant-setup.md`, and the Overleaf handout copy synchronized before delivery

## Parallel track — May 18 workshop & AI OS install tiers *(added 2026-05-05)*

Solo build for the 2026-05-18 departmental methods-lunch workshop (90 min, 12-1:30pm). Ships a modular AI OS install package in three tiers, plus a new 90-min deck and lightly-refreshed seminar page. Approach: build tier (a) first, then deconstruct into (b) and (c). Sanitization stance is **scaffolding only** — keep skeleton + minimal seed, strip private content. Cross-harness wiring covers **Claude Code + Codex** (no Antigravity in v1). Critical-path item is tier (a) sanitization; risk concentration is solo build under ~3-day window.

### Phase 0 — Install-tier spec *(blocks all build phases)*

- [ ] Define entry-point and `README.md` template for each of the three tiers
- [ ] Inventory which files/folders ship with each tier
- [ ] Decide repo location — proposed: `workshop-package/install-tiers/{full-os,skeleton,project-only}/`
- [ ] Sign-off pass with researcher before any sanitization

### Phase 1 — Tier (a): sanitized full AI OS *(keystone)*

- [ ] Replicate `personal/` folder structure (CLAUDE.md, `memory/`, `skills/`, `personas/`, `agents/`, `identity/`)
- [ ] Seed minimal content: 1 persona (proposed: `chief-of-staff`); 2-3 skills (proposed: `project-setup`, `skill-writing`, `persona-writing`); 1 worked-example row in `projects-ledger.md`; empty/template versions of `chief-of-staff-log.md`, `connector-update-queue.md`, `identity-update-queue.md`, `skill-usage.log`
- [ ] Strip private content from `~/.claude/CLAUDE.md` template, replace identity block with `{{PLACEHOLDER}}` tokens
- [ ] Cross-harness wiring: `.claude/` (Claude Code) + `AGENTS.md` (Codex)
- [ ] Install instructions for Windows + Mac at root README

### Phase 2 — Tier (b): skeleton (meta-skills bundle, derived from a)

- [ ] Identity-building skill (interview → fills `~/.claude/CLAUDE.md` template)
- [ ] Persona-building skill (sanitize from existing `persona-writing-protocol.md`)
- [ ] Skill-building skill (sanitize from existing `skill-writing-protocol.md`)
- [ ] IDE-wiring skill (Claude Code + Codex setup walkthrough)
- [ ] Bundle `project-setup` from (a)
- [ ] README explains "build your OS from scratch" vs. tier (a)'s seeded scaffold

### Phase 3 — Tier (c): project-only (derived from a/b)

- [ ] Single-folder drop with `project-setup.md` + `project-setup-existing.md` + minimal README
- [ ] No identity, no personas, no skill library

### Phase 4 — Slide deck (90-min flow)

- [ ] New deck file in Overleaf at `C:\Users\spaci\Dropbox\Apps\Overleaf\AI in the Research Process\` (filename TBD)
- [ ] §1 Framing: control + transparency (~10 min)
- [ ] §2 Fundamentals: vocabulary + 5-layer stack (~20 min)
- [ ] §3 Live demo (Simone-driven, no code-along) (~25 min)
- [ ] §4 Best-practices framework (~20 min)
- [ ] §5 Install-and-go: three tiers + when to pick each (~10 min)
- [ ] §6 Q&A buffer + closing

### Phase 5 — Companion artifacts

- [ ] Light rewrite of `docs/seminar.md` — evergreen, no May-18 mention; remove "code along" language; add tier-choice language; keep download links
- [ ] Participant first-session handout (1 page) — tier choice + install steps + first 30 min after the workshop

### Phase 6 — Connector + project metadata

- [ ] Wire Overleaf connector: register `C:\Users\spaci\Dropbox\Apps\Overleaf\AI in the Research Process\` in project `README.md` (precedent: existing "Skills" section pattern)
- [ ] Append Overleaf path to `personal/CLAUDE.md` connector list if cross-session awareness wanted
- [ ] Update `personal/memory/projects-ledger/ai-in-social-science-research.md`: fill `overleaf linked` field

### Phase 7 — Dry run *(do not skip)*

- [ ] Install tier (a) on a clean folder, run through first-session walkthrough
- [ ] Install tier (b), bootstrap a fake OS from scratch
- [ ] Install tier (c), run `project-setup` on a sandbox
- [ ] Walk the deck end-to-end with stopwatch, confirm 90-min fits

### Descope levers if the 3-day window squeezes

- Defer (b) and (c) to v2, ship only (a) on May 18 with a "lower-tier versions coming" note. Loses the modular pitch but keeps the keystone.
- Defer the participant handout, replace with a slide at the end of the deck. Saves ~half a day.
- Skip dry-run for tiers (b)/(c) if derived mechanically from (a). Risky — installer issues are the most likely live-workshop embarrassment vector.

## Stage 6 — Review & Submission

- [ ] Internal coherence pass (arguments, citations, figures)
- [ ] Verify every claim in `asset-registry.csv` to `human-verified`
- [ ] Advisor / colleague feedback round (save to `background/feedback/`)
- [ ] Final LaTeX build in Overleaf
- [ ] Submit
