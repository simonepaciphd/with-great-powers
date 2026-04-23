# Literature Review Protocol

A four-phase skill for running a structured, agent-assisted literature review that produces a Zotero-compatible bibliography and a per-source classification mapped to the paper's sections. Designed to compose with the `project-setup.md` protocol (writes to `background/literature/` per that folder convention).

Companion asset: **`lit-review-prompt-template.md`** (in this Skills folder) is the permanent, project-agnostic agent-facing prompt. This protocol (Phase 2) produces per-strand *context* files that get pasted alongside the template when the caller runs a search.

Governing principles: **researcher control** and **radical transparency**. The agent **never** decides on its own what to research, how broadly to scope, or how to rank sources. Every phase begins with an interview that gets explicit researcher sign-off before the agent commits anything to disk.

---

## When to use

- A new paper / chapter needs a literature review.
- An existing paper needs to expand its literature in a particular direction.
- An agent has produced raw literature output that needs to be normalized and filed.

## Artifacts the protocol produces

Under `background/literature/` of the active project:

Top level:
1. `lit-review-strategy.md` — strand list (scope definition, Phase 1).
2. `lit-review-prompts.md` — index + status tracker of per-strand prompts (Phase 2).
3. `references.bib` — BibTeX file, aggregated from ai- and human-inputs (Zotero import target).
4. `classification.csv` — source-level tagging and section mapping.

Subfolders (provenance split):
5. `ai-inputs/` — agent-authored material: summary notes, deep-research outputs. Starts at `partially-verified` at best.
   - `ai-inputs/lit-review-prompts/search-specific-prompts/` — one file per strand, holding the filled *prompt context* block plus tracking (status, raw-output destination, ingestion checklist). This is the editing surface as RQs / anchors / scope evolve; pair it with the permanent template when running a search.
   - `ai-inputs/lit-review-prompts/finalized-prompts/` — one file per strand, a pre-merged paste-ready prompt (template + context). This is what gets copy-pasted into the deep-research tool. Regenerate whenever either source file (template or search-specific prompt) changes.
6. `human-inputs/` — researcher-authored material: user's notes, annotated PDFs, Scholar exports, colleague recs, Zotero BibTeX exports. `human-verified` by authorship (upstream sources still need independent verification).

Per-source notes go in `ai-inputs/<citekey>.md` or `human-inputs/<citekey>.md` depending on who wrote the note. `references.bib` and `classification.csv` always live at the top level.

**Agent-facing prompt** lives in the Skills library as `lit-review-prompt-template.md`, not in the project. Project-side per-strand files provide only the caller-specific context (strand, questions, anchors, scope, exclusions, qualitative constraints). The search agent's stopping rule is diminishing returns, not a quota.

## Universal rules

1. **Interview first, act second.** Every phase below has a required interview checklist. Do not move to the *action* step of a phase until the researcher has answered the interview questions.
2. **Propose, don't decide.** When the agent has ideas (candidate strands, candidate citekeys, candidate source tiers), present them as a numbered list with clear "approve / edit / reject" options. Wait for the researcher's choice.
3. **Small commits.** After each phase, write only what was just agreed. Summarize the diff and ask whether to continue.
4. **Ambiguity beats fabrication.** If a source is ambiguous, flag it as ambiguous. Never invent DOIs, author order, or publication venues to "complete" an entry.

---

## Phase 1 — Scope the strands

Goal: turn the paper's outline into a short, named list of literature strands, approved by the researcher.

**Interview checklist** — ask these questions, wait for answers, then proceed:

1. *"In one sentence, what is the paper's thesis?"*
2. *"Name 3–5 interlocutors (people or papers) whose position the paper engages with. For each, is the paper **building on**, **arguing against**, or **responsibly citing** them?"*
3. *"Which sections of the outline absolutely need a literature review, and which sections are you comfortable writing from your own knowledge and existing notes?"*
4. *"How many strands? A tight review has fewer strands but each is run exhaustively; a wider review covers more ground with the same per-strand saturation rule."*
5. *"Any hard constraints on time window, disciplines, languages, or publication venues I should enforce for all strands?"*
6. *"Any strands you already know you want — give me names and a one-sentence scope for each."*

**Action step** — after the interview, draft a candidate strand list:

- Each strand gets:
  - **Name** (short, lowercase-kebab-case).
  - **Rationale** (1–2 sentences: why this strand, where it appears in the outline).
  - **Target sections** (outline §-numbers).
  - **Known anchor sources** (papers already in hand, if any).
  - **Qualitative constraints** (e.g., "include at least one skeptical voice") — **not** a source count. The search agent stops by diminishing-returns rule, not by quota.

Present to the researcher for approval / edits / additions / removals. Iterate until signed off. Save to `lit-review-strategy.md` only after sign-off.

**Interrupt back to user** before Phase 2.

---

## Phase 2 — Draft prompts

Goal: one prompt per approved strand, suitable for a deep-research or web-search agent.

**Interview checklist**:

1. *"Which deep-research tools will you use? (ChatGPT Deep Research, Claude research agents, Elicit, Perplexity, other.) Different tools have different prompt conventions; I'll tune accordingly."*
2. *"For each strand, what 2–4 research questions should the prompt specifically answer?"* (Ask one strand at a time if the list is long.)
3. *"Any sources you explicitly want the agent to find (anchor references) or to avoid (e.g., known-bad sources, papers you've already dismissed)?"*
4. *"Preferred output volume per strand — count of sources? reading time budget?"*
5. *"How aggressive should the skepticism filter be? Strict peer-reviewed only, or include high-signal working papers and blog posts?"*

**Action step** — for each approved strand:

1. Create a file at `background/literature/ai-inputs/lit-review-prompts/search-specific-prompts/<strand>.md` containing the *prompt context* block plus tracking scaffolding (status, raw-output destination, ingestion checklist). The agent-facing task description is in the permanent template — do not duplicate it into per-strand files.
2. **Final merging step** — produce the paste-ready file at `background/literature/ai-inputs/lit-review-prompts/finalized-prompts/<strand>.md` = the contents of `Skills/lit-review-prompt-template.md` (from `## Role and conduct` through `## Non-negotiable rules`) followed by the `## Prompt context` block lifted from the search-specific file. This merged file is what the researcher pastes into the deep-research tool. **Regenerate** it whenever the template or the search-specific context changes.

Per-strand file skeleton (for `search-specific-prompts/<strand>.md`):

```
# <strand-id> — <strand-name>

**Strand:** <strand-id> — <strand-name>
**Status:** draft | ready-to-run | running | output-received | ingested

**To execute:** Use the pre-merged file at
`../finalized-prompts/<strand>.md` — it combines the template +
the "Prompt context" block below. Paste the agent's output into the
"Raw output" section below when received. If the context block changes,
regenerate the finalized file.

---

## Prompt context

### Paper context
- Title: <paper title>
- Thesis: <one sentence>

### Strand
- ID: <strand-id>   *(used by the template to name downloads: `<strand-id>-references.bib`, `<strand-id>-summary.md`; match the finalized-prompt filename stem, e.g., `A1-ai-in-the-research-process`)*
- Name: <strand-name>

### Research questions
1. <researcher-supplied>
2. <researcher-supplied>

### Anchor sources (do not re-discover — find adjacent work)
- <citation + URL>

### Scope overrides (if any)
- Time window, disciplines, publication types, languages.

### Exclusions
- <items to avoid>

### Additional constraints
- e.g., "include at least one skeptical voice."

---

## Raw output (fill after run)

[paste agent output here]

---

## Ingestion checklist
- [ ] BibTeX entries validated
- [ ] Each URL/DOI verified
- [ ] Deduped against existing `references.bib`
- [ ] Entries appended to `references.bib`
- [ ] Rows added to `classification.csv`
- [ ] `asset-registry.csv` updated
- [ ] `interaction-log.csv` updated
```

Update the top-level `lit-review-prompts.md` to act as an **index** — strand ID, path to the search-specific file, path to the finalized file, status — rather than holding the full prompt text.

**Interrupt back to user** for review of each strand's context block before it is merged into a finalized prompt and executed.

---

## Phase 3 — Ingest

Goal: convert agent + researcher output into a single `references.bib` plus a parallel `classification.csv` row per source.

**Interview checklist**:

1. *"Where is the raw output? (paste into chat, drop into the per-strand file at `background/literature/ai-inputs/lit-review-prompts/<strand>.md` under the 'Raw output' section, or paste a file I should ingest.)"*
2. *"For sources from your own Google Scholar / Connected Papers / colleague recs, how will you hand them to me — BibTeX export, full-text PDFs, just titles?"*
3. *"Do you have a preferred citekey style (e.g., `spirling2023`, `spirling2023nature`, `Spirling2023`)? Default is lowercase `<lastname><year><shortword>`."*
4. *"Any duplicates you've already noticed across strands I should watch for?"*

**Action step**:

1. Normalize each incoming source:
   - Validate BibTeX (required: author, title, year; one of journal/booktitle/publisher; doi or url).
   - Check every DOI resolves. Mark any that don't `VERIFY`.
   - Dedupe by DOI / title against existing `references.bib`. Ask researcher how to resolve conflicts.
2. Append verified entries to `references.bib`, keeping the file sorted by citekey.
3. Add a row to `classification.csv` for each new source. Fill `strand`, `evidence_type`, `reliability`, `sections` from the agent output — but tag `read_status = unread` and `verification = partially-verified` until the researcher reads.
4. Register each BibTeX citekey in `asset-registry.csv` with `asset_type = reference`.
5. Log the session in `interaction-log.csv`.

**Interrupt back to user** with a diff summary: "N new entries, M duplicates resolved, K flagged VERIFY."

**Zotero import**: *File → Import → BibTeX* on `references.bib`. For two-way sync use Better BibTeX. Keep `references.bib` as source of truth.

---

## Phase 4 — Classify & map

Goal: every BibTeX entry has a complete `classification.csv` row. High-reliability sources and sources the researcher plans to cite get a deep note. The researcher can see at a glance where each source is going in the paper.

**Interview checklist** (only the first time; later cycles can skip this):

1. *"For this paper, do you want section tags at the subsection level (e.g., `3.1`) or the section level (`3`)?"*
2. *"How do you want to handle sources that deserve a per-source markdown note? Options: always for high-reliability sources; only sources you plan to cite; only sources for quote extraction; never."*

**Action step**:

1. For each new entry added in Phase 3, present the agent's proposed classification (strand, sections, evidence type, reliability) to the researcher for approval or edit.
2. Once approved, `verification` stays at `partially-verified` until the researcher reads and marks `read_status = read`.
3. For sources the researcher plans to cite or quote, generate `<citekey>.md` with: thesis, method, key evidence, limitations, quote candidates, usable in which paper section.

**Review cadence**:
- Before submission, verify every source cited in the paper has `verification = human-verified` AND `read_status = read`.
- Sources found but not cited can remain `skimmed` or `unread` as long as they stay in the registry for reviewer-response readiness.

---

## Phase 5 — Maintain (continuous)

- New sources found mid-drafting → run through phases 3–4 directly; do not open a new strand unless the researcher approves.
- If a new strand emerges, run the Phase 1 interview for that strand only and extend `lit-review-strategy.md`.
- Weekly: diff `references.bib` against `classification.csv`. Any mismatch is a bug — either an unclassified entry or a row without a BibTeX backing.

---

## `classification.csv` schema

| Column | Values |
|--------|--------|
| `citekey` | BibTeX key (matches `references.bib`) |
| `strand` | Comma-separated strand names (from `lit-review-strategy.md`) |
| `reliability` | high \| medium \| low (as flagged by the search agent per the prompt template) |
| `sections` | Comma-separated outline sections (e.g., `1.1,3.1,4.2`) |
| `evidence_type` | empirical \| conceptual \| methodological \| normative \| review |
| `read_status` | unread \| skimmed \| read |
| `verification` | not-verified \| partially-verified \| human-verified |
| `note_file` | Path to `background/literature/<citekey>.md` if a deep note exists |
| `notes` | One-line hook |

No researcher-facing importance tier column. Importance emerges from `sections` (where the source will be cited) and `read_status` (how deeply it has been engaged with).

## `references.bib` conventions

- UTF-8, LF line endings.
- One entry per source, sorted by citekey.
- Citekey format: `<lastname><year><shortword>` (e.g., `spirling2023nature`).
- Always include `doi` or `url`.
- Ad-hoc notes go in `annotation = {...}` (Zotero preserves).

## Handoff with other skills / protocols

- Writes to `background/literature/`, defined by `project-setup.md`.
- Each new `references.bib` entry → a row in `asset-registry.csv` (per Rule 4 of `project-setup.md`).
- Each agent session that produces sources → a row in `interaction-log.csv` (per Rule 5).
- `paper-writing-protocol.md` consumes `references.bib` + `classification.csv` when drafting.

## Rules inherited from the prompt template

The companion template (`lit-review-prompt-template.md`) already enforces — on the search agent — a source-type hierarchy (peer-reviewed > working papers > institutional reports > …), per-source reliability tiering (`high` / `medium` / `low`), a `PENDING` section for inaccessible-but-relevant sources, a strict two-artifact output with **strand-id-prefixed filenames** (`<strand-id>-references.bib`, `<strand-id>-summary.md`) so multiple strand downloads don't collide, and non-negotiable rules (no fabrication, no training-memory summaries, final verification pass). Phase 3 ingestion here checks that the output actually conforms; escalate if it doesn't (and in particular, reject outputs with generic filenames like `references.bib` / `summary.md` — they signal the template was bypassed or the strand-id was omitted).

## Common failure modes

- **Fabricated citations.** Agents will invent DOIs. Require at least one working URL per entry and spot-check. Flag any source without a resolvable URL as `VERIFY` and never merge into `references.bib` unverified.
- **Scope creep without sign-off.** A strand that keeps growing is a sign it should split or that the paper's scope needs tightening. Stop and ask.
- **Vendor-survey numbers treated as facts.** Industry surveys (McKinsey, Wiley, Gartner) should be `partially-verified` at best; always cite with methodology caveat.
- **Silent classification.** The agent quietly tagging sources is the opposite of this protocol's intent — every classification decision surfaces to the researcher.
- **Template bypass.** If a search was run without the permanent prompt template (e.g., the caller wrote their own prompt on the fly), mark *all* results `partially-verified` regardless of source reliability. The template's rules are what justify higher verification tiers.
