# Skills-Library Setup Protocol

A five-phase skill for standing up a personal (or lab-level) skills library from scratch: pick a location, pick a *librarian* pattern (how agents find and load skills), seed the library with a small starter set, wire it into the active harness and projects, and test on one invocation.

Designed to compose with `project-setup.md` and `project-setup-existing.md` — both dispatch to this protocol when they detect no existing library — and with `skill-writing.md`, which adds every newly authored skill back into the library via Phase 3.

Governing principles: **researcher control** and **radical transparency**. The protocol never decides on its own where the library should live or how it should be organized. The researcher picks, the protocol surfaces trade-offs, and every commit waits for explicit sign-off.

---

## When to use

- The researcher has no existing skills library and wants to start one.
- An existing ad-hoc collection of skills, prompts, or templates (`prompts/`, `templates/`, a single `CLAUDE.md`, a Notion page) should be consolidated into a proper library.
- A lab or team wants to stand up a shared library all members can reach.

Do **not** use this skill when a library already exists and the researcher only wants to add one more skill (use `skill-writing.md`), when the real need is a single project-local playbook that does not justify cross-project reuse, or when the researcher has not yet drafted even one skill — write the first skill first, then come back.

## Artifacts the skill produces

1. `<library-root>/` — the library folder at the chosen path.
2. `<library-root>/README.md` — the index: one row per skill with name, one-sentence purpose, trigger keywords, and relative path.
3. `<library-root>/<starter-skill>.md` files — starter skills copied in, typically `skill-writing-protocol.md`, `project-setup.md`, plus any skills the researcher has already drafted.
4. A "Skills" pointer block in the active project's `README.md` (and optionally in a harness-global config file) giving the library path so every agent instance can find it.
5. If called from within a project: a row in `asset-registry.csv` for each starter skill copied in, and a row in `interaction-log.csv` for the setup session.

## Universal rules

1. **Interview first, commit second.** Every phase has an interview step. Do not create folders, copy files, or edit harness config until the researcher has answered the questions in the current phase.
2. **Surface trade-offs, don't pick for the researcher.** Location, librarian pattern, and starter seed are all choices the researcher owns. Present options as numbered lists with a clear trade-off line each.
3. **Small seed beats big dump.** A library that starts with three well-tested skills is more useful than one that starts with twenty speculative ones. Copy in only skills the researcher has actually used or is committed to using this month.
4. **The library is a first-class asset.** It should be version-controlled or otherwise backed up from day one. Propose a backup strategy even if the researcher defers the mechanics.
5. **Librarian over library.** The orchestration pattern — how agents find and load the right skill — matters more than any individual skill file. A well-indexed library of ten skills beats an unindexed heap of a hundred.

---

## Phase 0 — Confirm the need

Goal: verify that a new library is actually the right response, and discover any existing material that should be consolidated rather than bypassed.

**Interview checklist:**

1. *"Do you already have a folder of skills, prompts, or templates anywhere? Including under informal names: `prompts/`, `templates/`, `.cursorrules`, a `CLAUDE.md`, a Notion page, a Dropbox note. If yes, we should consolidate rather than start fresh."*
2. *"How many skills do you expect to have within six months — three, ten, fifty?"* This calibrates the librarian choice in Phase 2.
3. *"Is this library for you alone, or for a lab or team?"* Changes the location and the versioning defaults.
4. *"Which harness(es) do you work in — Claude Code, Codex, Cursor, Antigravity, multiple? Different harnesses have different preferred paths and different native skill mechanisms."*

**Action step:** write a one-paragraph scope statement covering single-user vs. team, expected size, and primary harness. Get sign-off before continuing.

---

## Phase 1 — Choose the library location

Goal: pick an absolute path for the library root, with a backup strategy named.

**Interview checklist:**

1. *"Should the library be available on every machine you use? If yes, we want a synced location (Dropbox, iCloud, OneDrive, or a git repo you clone everywhere)."*
2. *"Do you want version history? A git repo gives you diffs and rollback; a cloud-synced folder gives you multi-device sync but only shallow history."*
3. *"Does your harness expect skills in a specific path? Claude Code looks under `~/.claude/skills/`; other harnesses have their own conventions. If yes, either use that path directly or symlink from it to your chosen canonical location."*
4. *"For teams: is the library going in a shared git repo, a shared cloud folder, or an institutional drive? Who has write access? Is there a review requirement before skills are added?"*

**Candidate locations — present as a numbered list with trade-offs:**

1. **Cloud-synced folder** (e.g., `~/Dropbox/Skills/`). Easy multi-device; informal history; no diffs.
2. **Git repo** (e.g., `~/repos/skills/`, optionally mirrored to GitHub). Full history; diffable; requires commit discipline.
3. **Harness-native path** (e.g., `~/.claude/skills/`). Lowest-friction invocation; harness lock-in; often unsynced across machines unless combined with option 1 or 2.
4. **Hybrid** — canonical copy in Dropbox or git, symlinked into the harness-native path. Best of both worlds at the cost of one extra step at setup.

**Action step:** record the chosen path as `<library-root>` in the scope statement. Create the folder. Do not copy skills in yet.

---

## Phase 2 — Choose the librarian pattern

Goal: pick how agents will find and load skills when invoked. This is the *librarian* of the library — the mechanism through which content becomes discoverable.

**Interview checklist:**

1. *"When an agent needs a skill, how should it find the right one? Three common patterns: (a) read a top-level index file and pick by keyword; (b) scan the folder and read each file's frontmatter to match on triggers; (c) rely on the harness's built-in skills registration."*
2. *"Do you want a flat layout (all skills at the library root) or a nested one grouped by category (e.g., `orchestration/`, `research-methods/`, `writing/`, `meta/`)?"* Flat is almost always the right answer for the first ten skills.
3. *"Naming convention: `<skill-name>.md`, `<skill-name>-protocol.md`, or something else? Consistency matters more than the specific convention."*

**Librarian patterns — present as a numbered list with trade-offs:**

1. **Index-first.** A `README.md` at the library root lists every skill in a table (name, one-sentence purpose, trigger keywords, path). The agent reads the README, picks a skill, then loads only that file. Harness-agnostic. Requires manual index maintenance when skills are added.
2. **Frontmatter-discovery.** Each skill file begins with a YAML frontmatter block listing `name`, `description`, `triggers`, and `tags`. The agent scans the library, reads frontmatter only, and loads the full body only after selection. No central index to maintain; requires harness support for a scan-then-load step.
3. **Harness-native.** The harness (e.g., Claude Code's skills mechanism) knows about the library and invokes skills by name or trigger directly. Lowest-friction invocation; strongest lock-in if you ever switch harness.
4. **Hybrid.** Harness-native primary, with an index `README.md` as a human-readable fallback and as a source of truth if the harness's registration format changes. Recommended default for a researcher who expects to work across multiple harnesses over time.

**Action step:** write the chosen pattern into the scope statement, then scaffold:

- If index-first or hybrid: draft a `README.md` with a table header and no rows yet.
- If frontmatter-discovery: write a `CONVENTIONS.md` (or a short header comment) specifying the required frontmatter schema.
- If harness-native: document in `README.md` which harness and which registration path is expected, so a reader landing in the folder years later knows how it was meant to be used.

Present the scaffold to the researcher. Do not copy skills in until sign-off.

---

## Phase 3 — Seed with starter skills

Goal: copy a small, deliberate set of skills into the library, with each row in the index or each frontmatter block filled in.

**Interview checklist:**

1. *"Which skills do you already have drafted that should go in? Names or paths."*
2. *"For the starter set, do you want the meta-skills (`skill-writing`, `project-setup`) from the *With Great Powers* chapter? They compose directly with this one."*
3. *"Anything half-drafted you want me to leave out until it has been tested at least once?"* Enforces the "small seed beats big dump" rule.
4. *"For each skill going in, what are the 2–5 trigger keywords that should reliably surface it?"*

**Action step:** for each approved skill:

1. Copy the file into `<library-root>/` (flat) or the chosen category folder (nested).
2. If using index-first or hybrid: append a row to `README.md` with name, one-sentence purpose, trigger keywords, and relative path.
3. If using frontmatter-discovery: verify the file has a valid frontmatter block; write one if missing, confirming each field with the researcher.
4. Report a compact summary diff to the researcher (files copied, rows added) before moving to Phase 4.

---

## Phase 4 — Wire the library into harnesses and projects

Goal: close the loop so agents in the researcher's actual workflows can find the library without further prompting.

**Interview checklist:**

1. *"Which harness or harnesses should know about this library right now?"*
2. *"Is there an active project that should immediately point at the library? If yes, what is the project root?"*
3. *"Should we also add the library pointer to a harness-global config file (e.g., a top-level `CLAUDE.md` in your home directory) so future projects inherit it automatically?"*

**Action step:**

1. If the harness has a skills path and you chose the hybrid location, symlink (or copy, per the Phase 1 decision) the canonical library into the harness path.
2. Add a "Skills" block to the active project's `README.md`:

   ```markdown
   ## Skills

   - Library: `<library-root>`
   - For any complex task, check the library first. If no skill fits, ask the user whether to create one before improvising.
   ```

3. If requested, add the same pointer to any global config file the harness reads.
4. If this protocol was invoked from inside a project, register the library as a `reference` asset in `asset-registry.csv` with `creator = mixed` (the researcher chose, the skill built), and note each starter skill copied in.

---

## Phase 5 — Test and iterate

Goal: the first real invocation is the final phase of setup.

**Action step:**

1. Start a fresh agent instance in any project and give it a task that should trigger one of the seeded skills. Watch whether it finds and loads the right skill without further prompting.
2. If it does not, diagnose at the level of the failure: was it the index (skill not listed), the trigger keywords (too narrow or too broad), the location (harness cannot reach it), or the prompt (did not cue the skill)? Fix at that level; do not escalate to a library-wide refactor.
3. Log the session in `interaction-log.csv` if this protocol was invoked from inside a project.

**Review cadence:**

- After the first three skill invocations, revisit the index and trigger keywords and adjust.
- Every six months, audit the library: prune stale skills, consolidate duplicates, and promote project-local skills that have proven reusable.

---

## Librarian patterns — reference

| Pattern | Discovery mechanism | Strengths | Weaknesses |
|---|---|---|---|
| Index-first | Agent reads `README.md` table | Harness-agnostic; transparent; debuggable by a human | Manual index maintenance |
| Frontmatter-discovery | Agent scans files and reads frontmatter only | No central index to rot; self-describing files | Needs harness support for scan-then-load |
| Harness-native | Harness registration API | Lowest-friction invocation | Harness lock-in; opaque to other tools |
| Hybrid | Harness-native + index fallback | Robust to harness changes; debuggable | Slightly more to maintain |

## Handoff with other skills

- `project-setup.md` and `project-setup-existing.md`: dispatch to this protocol when they detect no existing library. Return the chosen `<library-root>` so they can write it into the project's `README.md` Skills block.
- `skill-writing.md`: every new skill produced by that protocol is added to this library via Phase 3 (append a row or write frontmatter, copy the file in).
- `lit-review-protocol.md` and any other composed skill: no direct handoff, but this protocol is their upstream dependency — without a library, none of them have a canonical home.

## Common failure modes

- **Premature library.** The researcher sets up a library before having any skills to put in it. Symptom: an empty `README.md` that rots. Recovery: write at least one skill via `skill-writing.md` before running this protocol, or wait until three drafts accumulate.
- **Over-categorization.** The researcher picks a nested layout with eight folders when they have four skills. Symptom: skills scattered across near-empty directories, each nearly impossible to search. Recovery: start flat, refactor into categories only when a category has three or more skills.
- **Orphaned global path.** Library sits in the harness-native path with no cross-machine sync, so it disappears when the researcher switches machines. Recovery: move the canonical copy to a synced location (Dropbox or git) and symlink into the harness path.
- **Unmaintained index.** New skills added to the folder but not to the index. Symptom: agents cannot find them even though the files exist. Recovery: either switch to frontmatter-discovery, or add an index-update line to the universal rules of `skill-writing.md` so new skills cannot land without an index entry.
- **Trigger-keyword collisions.** Two skills match the same keyword; the agent picks the wrong one. Recovery: add disambiguating keywords and a "see also" pointer on the losing skill; in extreme cases, narrow the broader skill's name.
- **Silent harness lock-in.** The researcher picks harness-native registration without realizing how hard the skills will be to use if they switch harness. Recovery: retrofit an index `README.md` after the fact; this is usually cheap and worth doing prophylactically.

## Worked example

A first-time user of agentic AI, with one drafted skill for running qualitative interviews, runs this protocol:

1. *Phase 0:* scope statement reads "single-user library, expected 5–10 skills within six months, primary harness Claude Code."
2. *Phase 1:* picks a hybrid location — canonical copy at `~/Dropbox/Skills/`, symlinked to `~/.claude/skills/`.
3. *Phase 2:* picks index-first because the library will stay small; scaffolds a flat `README.md` with a three-column table (skill, purpose, triggers).
4. *Phase 3:* copies the interview skill in and appends a row. Declines to add the chapter's meta-skills for now because they want to read them first.
5. *Phase 4:* adds a "Skills" block to the one active project pointing at `~/Dropbox/Skills/`; declines a harness-global config entry for now.
6. *Phase 5:* first invocation in that project does not surface the interview skill because the prompt used the word "qualitative" but the triggers only listed "interview"; adds "qualitative" and "semi-structured" to the triggers and re-runs. Works.

Total time: about 45 minutes of researcher attention, mostly in Phases 1–2.
