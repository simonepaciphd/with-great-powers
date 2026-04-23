# Project Setup Protocol — Existing Projects

Companion to `project-setup.md`. Use this skill when a researcher wants to bring agentic workflow into a project that is **already underway** — folders exist, files have accumulated, sometimes years of history are on disk — and starting from the blank template is not an option. The skill inventories what is already there, lays out three retrofit depths (full restructure / selective additions / minimal adoption), and produces a concrete move list the researcher signs off on before any file is touched.

Governing principles: **researcher control** (no rename, move, or deletion without explicit sign-off) and **radical transparency** (the existing state is documented before anything changes, and every retrofit move is itself logged).

---

## When to use

- The researcher wants to adopt agentic workflow on a project that already has its own folder structure, naming conventions, and accumulated assets.
- A collaborator's project needs to be brought into a shared agentic workflow without forcing that collaborator onto a new layout.
- A long-running project is approaching a phase (replication package, handoff, submission) where provenance tracking becomes load-bearing and retrofit is now worth the cost.

Do not use when:

- The project is genuinely new or only has a handful of placeholder files — run `project-setup.md` instead.
- The project is a read-only archive or a dataset snapshot where no new assets will be produced.
- The researcher has not yet decided whether they want to adopt the workflow at all — in that case, walk them through the full `project-setup.md` template first, then return here to decide on depth.

## Artifacts the skill produces

1. `existing-structure.md` (temporary, in a scratch location the researcher approves) — the inventory produced in Phase 1.
2. A retrofit plan (temporary) — the approved move list from Phase 3.
3. Depending on the depth chosen in Phase 2:
   - **Option A (Full restructure):** the full folder tree from `project-setup.md`, with existing files moved into place; a filled-in `README.md`, `implementation-roadmap.md`, `asset-registry.csv`, `interaction-log.csv`.
   - **Option B (Selective additions):** whichever subset of the template folders + ledgers closes real gaps; a filled-in `README.md` that names the hybrid layout.
   - **Option C (Minimal adoption):** one agent-facing folder (default name `agent-workspace/`, researcher-renameable) at project root, plus `asset-registry.csv` and `interaction-log.csv` at project root, plus a short `README.md` section describing the adoption.
4. A row in each ledger logging the retrofit session itself.

## Universal rules

1. **Inventory before proposing.** Do not suggest a retrofit depth until Phase 1 has produced a written map of what already exists.
2. **Three options, not one.** Always present all three retrofit depths with their trade-offs, even when one looks obviously right. The researcher's call.
3. **No moves without sign-off.** Phase 3 produces a plan. Phase 4 executes it. Do not collapse these phases — the plan is the checkpoint.
4. **Preserve external sync.** Before moving or renaming any folder, check what outside systems depend on its path (Overleaf sync, GitHub remotes, CI, collaborator links, bibliography paths). Flag each dependency in the Phase 3 plan.
5. **Backfill conservatively.** When populating `asset-registry.csv` for pre-existing assets, default `verification = not-verified` or `partially-verified`. Never assign `human-verified` to a file the researcher has not re-read in this session.
6. **Archive, don't delete.** If the retrofit displaces files, move them to the nearest `archive/` subfolder rather than deleting. Applies even when the displaced file looks obsolete.
7. **Minimal first, restructure last.** When in doubt, prefer the lowest-impact option that closes the gap the researcher named. Restructures are expensive and their benefits compound slowly.

---

## Phase 0 — Confirm this is the right skill

Goal: verify the project is actually an existing-project retrofit, not a new-project setup in disguise.

**Interview checklist:**

1. *"How old is the project, roughly, and how many files does the current folder hold?"*
2. *"What outside systems (Overleaf, GitHub, cloud drives, a co-author's machine) are synced to this folder or depend on its current paths?"*
3. *"What is the concrete trigger for adopting agentic workflow now — a submission deadline, a replication handoff, a collaborator onboarding, general cleanup?"*
4. *"Have you already started the `project-setup.md` protocol in this folder and bailed out, or is this the first attempt?"*

**Action step:** if the project is near-empty or the researcher has not yet committed to agentic workflow, hand off to `project-setup.md` and stop. Otherwise, write a one-paragraph scope statement naming the project, the trigger, and any external sync constraints. Get sign-off before continuing.

---

## Phase 1 — Map the existing structure

Goal: produce a written inventory of the current folder before proposing any changes.

**Interview checklist:**

1. *"Which folders are load-bearing (you actively work in them) versus legacy (present but untouched)?"*
2. *"Are there files whose location or name is dictated by an outside system (bibliography path, Overleaf `\input` path, script that reads a fixed filename)?"*
3. *"Is there already anything that functions as an asset registry or interaction log, even informally — a notes file, a changelog, a README?"*

**Action step:** dispatch a subagent (fresh context, scoped task) to traverse the folder and produce `existing-structure.md` with:

- Folder tree, one level per heading, with a one-line purpose note next to each folder (inferred from contents).
- File counts and rough size per folder.
- Naming conventions detected (dates, underscores, version suffixes).
- Candidate "matches" for each slot in the `project-setup.md` template — e.g., `papers/` might match `background/literature/`; `code/` might match `scripts/`.
- Gaps — slots in the template with no existing counterpart.
- External-sync dependencies flagged per folder (from Phase 0 answers).

Present the inventory back to the researcher for correction. Do not move to Phase 2 until they have confirmed the map is accurate.

---

## Phase 2 — Present the three retrofit options

Goal: give the researcher a real choice of depth, with honest trade-offs.

**Action step:** write each option as a short proposal the researcher can read in a minute. Template for each:

### Option A — Full restructure

Fold the existing project into the full `project-setup.md` tree. Every existing folder gets renamed or merged into the canonical slot; the four root files (`README.md`, `implementation-roadmap.md`, `asset-registry.csv`, `interaction-log.csv`) are created; the asset registry is backfilled with every existing file.

- **When it makes sense:** the project is early enough that external sync is shallow, the researcher wants this project to be a model of the workflow, the team benefits from a shared canonical layout.
- **Cost:** one to several days of research time; every external sync dependency has to be updated; git history gets a large rename commit that can complicate blame.
- **Risk:** highest. One broken path in Overleaf or a script is enough to stall work.

### Option B — Selective additions

Keep the existing layout. Add only the template folders whose absence is actually costing the researcher something — e.g., add `background/literature/` if literature is currently scattered, or add `appendix/` only when the project is approaching submission. Always add the two ledgers and a filled-in `README.md` that names the hybrid layout.

- **When it makes sense:** the project has a working layout the researcher is fluent in, but a few specific gaps are real.
- **Cost:** half a day to a day. Low friction.
- **Risk:** moderate. Hybrid layouts need a README that explains them, or a future collaborator will be confused.

### Option C — Minimal adoption

Touch the existing folders not at all. Add exactly three things at project root:

1. One agent-facing folder (default `agent-workspace/`, or whatever the researcher prefers) — scratch space for agent outputs, plans, intermediate notes, so agents never write into the researcher's working folders by surprise.
2. `asset-registry.csv` — schema per `project-setup.md`. Backfilled only to the extent the researcher wants; at minimum, populated going forward.
3. `interaction-log.csv` — schema per `project-setup.md`. Populated from this session onward.

Also add a short "Agentic workflow" section to the existing `README.md` (or a new `README.md` if none exists) describing the three additions and the path to the skill library.

- **When it makes sense:** the project layout works, outside-system dependencies are thick, the researcher wants provenance tracking without paying the cost of a restructure.
- **Cost:** under an hour.
- **Risk:** lowest.

**Interview checklist** (after presenting all three):

1. *"Which option do you want to pursue?"*
2. *"If Option A or B, are there any folders you explicitly want left untouched? Any renames you explicitly refuse?"*
3. *"For the minimal folder (Option C), what name should it have in this project?"*

**Action step:** record the choice and any constraints. Do not start moving files yet.

---

## Phase 3 — Retrofit plan & sign-off

Goal: produce a concrete, line-by-line plan before any file touches disk.

**Action step:** write the plan as an ordered list. Each item is one of:

- `MOVE <source> → <target>` with a note on whether external sync is affected.
- `RENAME <old> → <new>` with the same sync note.
- `CREATE <path>` with a one-line purpose.
- `ARCHIVE <source> → <archive path>` with a one-line reason.
- `BACKFILL asset-registry.csv` for a named list of existing files, with default `verification` values.
- `LEAVE <path>` for anything explicitly outside the retrofit (useful when the researcher has flagged a no-touch zone).

Read the plan back to the researcher. Ask: *"Any items to add, remove, or reorder? Any that should wait for a separate session?"* Do not proceed until the researcher gives explicit sign-off on the final list.

---

## Phase 4 — Execute the plan

Goal: apply the approved moves, and only the approved moves.

**Action step:**

1. Execute items in order. Stop and flag anything the plan did not explicitly list — do not improvise adjacent cleanup, even when it looks obvious.
2. After each external-sync-affecting move, pause and ask the researcher to verify the downstream system still works before continuing.
3. When creating the four root files (or the minimal subset for Option C), use the schemas and template text from `project-setup.md` verbatim. Do not write a variant schema.
4. When the plan finishes, produce a short "what changed" summary for the researcher: list the moves executed, the files created, and anything skipped.

---

## Phase 5 — Backfill the asset registry

Goal: populate `asset-registry.csv` with pre-existing assets at a level of fidelity the researcher chooses.

**Interview checklist:**

1. *"Do you want the registry backfilled for every existing asset, only for assets that will be touched in the next month, or only going forward?"*
2. *"For backfilled rows, what default should I use for `creator` when the creator is unclear — `human`, `mixed`, or leave blank for you to fill?"*
3. *"What default for `verification` — `not-verified` for everything, or `partially-verified` for anything the researcher has previously reviewed?"*

**Action step:** append rows in bulk per the researcher's choices. For any row where `creator` or `model_metadata` is genuinely unknown, leave the cell blank rather than guess. Flag the blank rows in the summary so the researcher can fill them opportunistically.

---

## Phase 6 — Wire the skill library

Goal: make the skill library discoverable from this project, at the lowest invocation friction the (harness × library-format) pair allows.

**Action step:**

1. If the researcher has no skill library, dispatch to `skills-library-setup.md` as a subagent first.
2. Dispatch to `skills-library-connection.md` with the project root and the library root. That protocol detects the harness, detects the library format (flat `.md` vs. Claude-Code-native `SKILL.md` directories), and picks the lowest-friction wiring — typically a harness-native copy or symlink, an instruction-file pointer (`CLAUDE.md` / `AGENTS.md` / `.cursorrules`), or pointer-plus-README. It always writes a "Skills" block to the project `README.md` as a harness-agnostic backstop.
3. If this retrofit produced any project-specific skills (likely not, but possible), note in the README whether they live in `appendix/` (replication-bound) or the global library (reusable).

---

## Handoff with other skills

- `project-setup.md`: called when Phase 0 concludes the project is actually new; also the source of the canonical folder tree, ledger schemas, and rule list reused here verbatim.
- `skills-library-setup.md`: called from Phase 6 when the researcher does not yet have a skill library.
- `skill-writing-protocol.md`: the protocol used to draft this skill, and the one to call if a project-specific skill needs to be written as part of the retrofit.
- `lit-review-protocol.md`: if Phase 1 reveals literature scattered across the project, the researcher may want to consolidate through a lit-review pass — that is a separate session, not part of the retrofit.

## Common failure modes

- **Restructure by default.** The agent proposes Option A because it looks tidiest, and the researcher accepts before understanding the external-sync cost. Symptom: the week after retrofit, a bibliography path breaks or an Overleaf `\input` fails. Recovery: default to Option C in the presentation, and require the researcher to argue up to B or A.
- **Skipping the inventory.** Phase 1 is cut short because the folder "looks simple." Symptom: Phase 4 surfaces a file the plan did not account for, and the agent improvises a destination. Recovery: re-run Phase 1 and amend the plan before continuing.
- **Aggressive backfill verification.** The agent marks old files `human-verified` because the researcher produced them. Symptom: downstream work trusts a claim the researcher has not re-read in a year. Recovery: rewrite all backfilled `verification` cells to `not-verified` or `partially-verified` unless the researcher explicitly re-reviewed the file in this session.
- **Silent deletion.** A displaced file is deleted rather than archived because it "looks redundant." Symptom: the researcher can't find a note they remembered writing. Recovery: restore from the nearest backup; add the archive rule to the project's `Rules for Agents` block.
- **Breaking external sync.** A folder rename breaks Overleaf or a CI path. Symptom: downstream build fails after the retrofit session. Recovery: revert the rename, add the dependency to the Phase 3 plan's sync-notes column, redo.

## Worked example

A researcher has been working on a diff-in-differences empirical project for eighteen months. Folder layout: `code/`, `data/`, `writeup/`, `misc/`. Overleaf syncs to `writeup/`. A co-author has a local clone with the same paths. Goal: bring this project under agentic workflow before a replication-package handoff three months out.

1. **Phase 0** — the researcher confirms the project is active, names the Overleaf sync and the co-author clone as external dependencies, and names the replication package as the trigger.
2. **Phase 1** — the subagent produces `existing-structure.md`: `code/` matches `scripts/` (further split needed: cleaning vs. analysis); `data/` matches `inputs/` (raw/clean split missing); `writeup/` matches `drafts/`; `misc/` is legacy and mostly archivable.
3. **Phase 2** — the researcher picks Option B (selective additions) because `code/` and `data/` should not be renamed (co-author sync) but the project lacks a literature folder, an appendix, and the two ledgers.
4. **Phase 3** — the plan: create `background/literature/`, `background/concepts/`, `appendix/`, `asset-registry.csv`, `interaction-log.csv`; move existing scattered literature PDFs from `misc/` into `background/literature/`; archive the rest of `misc/` into `misc/archive/`; leave `code/`, `data/`, `writeup/` untouched.
5. **Phase 4** — executed; the Overleaf sync is unaffected; the co-author is emailed the summary of what changed.
6. **Phase 5** — registry backfilled for `writeup/` drafts and `background/literature/` PDFs only, per the researcher's request; `code/` and `data/` will be backfilled opportunistically over the next month.
7. **Phase 6** — the existing skill library is already at `C:\Users\spaci\Dropbox\Skills\`; a "Skills" section is added to the new `README.md` pointing there.

Total time: about two hours of researcher attention, no external sync broken, registry populated enough to support the three-month push to submission.
