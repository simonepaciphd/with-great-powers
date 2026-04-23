# Skills-Library Connection Protocol

A short skill for **wiring a project to a skills library**. Given (i) a project folder with a `README.md` and (ii) a library root produced or confirmed by `skills-library-setup.md`, this protocol picks the lowest-friction mechanism for making library skills discoverable from inside the project, applies it, and always leaves a human-readable trail in the project `README.md`.

Composes with `project-setup.md` and `project-setup-existing.md` (both call this protocol after the project scaffold exists and a library path is known), `skills-library-setup.md` (provides the library path), and `skill-writing.md` (when a new skill is added to the library and needs to be re-surfaced in the active project).

Governing principles: **researcher control** and **radical transparency**. The wiring mechanism is a researcher choice, not a silent default. Whatever is chosen produces a visible artifact — a copy, a symlink, or a pointer line — that a future reader can audit.

---

## When to use

- Called from `project-setup.md` or `project-setup-existing.md` once both a project root and a library path exist.
- Standalone when the researcher has a project and a library that are not yet connected, or when the primary harness of a project changes (e.g., adding Codex alongside Claude Code).
- After `skill-writing.md` produces a new skill the researcher wants immediately discoverable from the active project.

Do **not** use when:

- No library exists yet — dispatch to `skills-library-setup.md` first and return here.
- The project has no `README.md` — run the relevant project-setup variant first.
- The library is already installed at the harness-global path the researcher uses (e.g., `~/.claude/skills/`) *and* the researcher has no replication or portability reason to also install it project-locally. In that case, confirm "no wiring needed" and stop.

## Artifacts the skill produces

Depending on the mechanism chosen, some combination of:

1. A `<project>/.claude/skills/` directory (Claude Code) or equivalent harness path, populated by copy or symlink.
2. A pointer block in `<project>/CLAUDE.md` (Claude Code), `<project>/AGENTS.md` (Codex), `<project>/.cursorrules` (Cursor), or the analog for other harnesses.
3. **Always:** a "Skills" block in `<project>/README.md` naming the library path, the mechanism used, and the resync cadence.
4. If invoked from inside a project with ledgers: rows in `asset-registry.csv` for each copied skill file, and a row in `interaction-log.csv` for the session.

## Universal rules

1. **Lowest friction at invocation, not at setup.** Prefer the mechanism with the fewest moving parts *when an agent actually runs*, even if it costs more at setup time. Setup is paid once; invocation is paid every time.
2. **Always leave a human-readable trail.** The `README.md` Skills block is written regardless of which harness-specific mechanism is also set up. If the harness mechanism later breaks or the researcher switches tools, the README survives.
3. **Respect the library format.** Do not silently transform the canonical library (e.g., wrapping flat `.md` files into `SKILL.md` directories) without explicit sign-off. Transformations are the domain of `skills-library-setup.md`, not this protocol.
4. **Project-scoped beats user-global when the project is replication-bound.** A replication package with `.claude/skills/` inside it is reproducible; a dependency on the author's `~/.claude/skills/` is not.
5. **Never edit harness-global config without explicit sign-off.** Project-local wiring is reversible; changes to files in the home directory affect every project.

---

## Phase 0 — Confirm prerequisites

Goal: verify the two inputs (project root, library root) and exit early when they are absent.

**Interview checklist:**

1. *"What is the absolute path to the project root?"*
2. *"What is the absolute path to the skills library?"* If unknown, dispatch to `skills-library-setup.md`.
3. *"Does the project already have a `README.md`?"* If not, dispatch to `project-setup.md` or `project-setup-existing.md`.

**Action step:** record both paths. Verify both exist on disk. Continue.

---

## Phase 1 — Detect harness and library format

Goal: collect the facts that determine which wiring is lowest-friction.

**Interview checklist:**

1. *"Which harness is primary for this project — Claude Code, Codex, Cursor, Antigravity, web chat, other, or multiple? If multiple, which one does the heaviest work?"*
2. *"Are the skills in your library stored as flat `.md` files, or as directories each containing a `SKILL.md` with YAML frontmatter (Claude Code's native format), or in some other structure?"*
3. *"Is this project expected to ship as a replication package, or stay single-machine?"* Changes the default between pointer and copy.
4. *"Are you the only agent user for this project, or will collaborators also run agents here?"* Collaborators change the default toward self-contained (copy) over pointer.

**Action step:** inventory the project folder for harness evidence (`.claude/`, `AGENTS.md`, `.cursorrules`, `.cursor/`, etc.) and the library folder for format evidence (flat `.md` vs. directories with `SKILL.md`). Record findings as a short table in the session context.

---

## Phase 2 — Pick the wiring mechanism

Goal: present three or four realistic options for the (harness × library-format) pair, recommend one, and get sign-off.

### The four mechanism families

**A. Harness-native install (copy).** Copy skills into the project's harness-native skills path (`<project>/.claude/skills/` for Claude Code, analogous for Cursor). Auto-discoverable by the harness at invocation; travels with the project. Drift risk if the canonical library updates later — mitigated by a declared resync cadence.

**B. Harness-native install (symlink).** Symlink the project's harness-native skills path to `<library-root>`. Zero drift; zero copy. Requires OS-level support for symlinks (on Windows, requires Developer Mode or admin privileges). Symlinks in git repos need explicit handling.

**C. Instruction-file pointer.** Add a "Skills" block to `<project>/CLAUDE.md` (Claude Code), `<project>/AGENTS.md` (Codex), `<project>/.cursorrules` (Cursor) naming the `<library-root>` path and the rule: *"check the library first for any complex task."* The harness reads its instruction file automatically, so every agent instance in the project sees the pointer. Low setup cost; one extra filesystem hop at invocation (the agent has to traverse to the library).

**D. README Skills block only.** A `## Skills` section in the project `README.md`. Harness-agnostic. Treated as universal rule 2 — **always applied** regardless of which of A–C is also in place, as a permanent backstop.

### Library-format caveat for Claude Code

Claude Code's native skill discovery requires each skill to be a **directory** containing a `SKILL.md` with YAML frontmatter (at minimum a `description:` field). A library of flat `.md` files is not auto-invoked by the native mechanism even if copied into `.claude/skills/` — the files will sit there as reference material, but the harness will not surface them at task time.

Two responses:

- **Accept the pointer pattern** (mechanism C): flat `.md` files stay where they are; the CLAUDE.md pointer tells agents to read them on demand. Lower setup cost; invocation friction is one explicit prompt read.
- **Wrap the library** (out of scope for this skill; handled by `skills-library-setup.md`): convert each `skill-name.md` into a `skill-name/SKILL.md` with minimum frontmatter. Then mechanism A or B applies normally. Higher one-time cost; auto-invocation afterward.

Surface this trade-off explicitly. Do not silently wrap the library.

### Recommendation matrix

| Harness | Library format | Replication-bound? | Recommended primary | Always apply |
|---|---|---|---|---|
| Claude Code | Native (dirs + SKILL.md) | Yes | **A** (copy into `<project>/.claude/skills/`) | D |
| Claude Code | Native (dirs + SKILL.md) | No | **B** (symlink), or **A** on Windows without Dev Mode | D |
| Claude Code | Flat `.md` | Yes | **C** (CLAUDE.md pointer) + manual copy of the subset the project uses | D |
| Claude Code | Flat `.md` | No | **C** (CLAUDE.md pointer) | D |
| Codex | Any | Any | **C** (AGENTS.md pointer) | D |
| Cursor | Native rule files | Any | **A** or **B** into `<project>/.cursor/rules/` | D |
| Web chat / no-filesystem | Any | — | **D** only; researcher pastes skill content into the custom-instructions field | — |
| Multiple harnesses | Any | Any | **C** for each harness's instruction file | D |

**Interview checklist** (after presenting the matrix):

1. *"Given the matrix, which primary mechanism do you want?"*
2. *"If mechanism A, what resync cadence — on demand (researcher re-runs this skill), on every setup invocation, never?"*
3. *"Should I apply the mechanism only at project level, or also to your harness-global config (e.g., `~/.claude/CLAUDE.md`)? The global version affects every project — requires explicit sign-off."*
4. *"Any skills in the library you explicitly want excluded from this project's wiring?"*

**Action step:** record the chosen mechanism, resync cadence, and exclusions.

---

## Phase 3 — Apply the wiring

Goal: execute the chosen mechanism end to end, finishing with the universal README block.

**Action step:**

1. **Mechanism A (copy):** for each approved skill in the library, copy into the harness path under `<project-root>`. For flat-`.md` libraries paired with Claude Code, copy as-is and expect mechanism C to do the invocation work. Append a row to `asset-registry.csv` per file with `creator = mixed`, `verification = not-verified`.

2. **Mechanism B (symlink):** on macOS/Linux, `ln -s <library-root> <project>/.claude/skills` (or the target directory per harness). On Windows, verify Developer Mode is on before attempting; fall back to A if not. Record the symlink in the project README's Skills block so a reader understands where the skills physically live.

3. **Mechanism C (pointer):** append or create a "Skills" block in the correct harness instruction file. Example for Claude Code at `<project>/CLAUDE.md`:

   ```markdown
   ## Skills

   Skills library: `<library-root>`
   Format: <flat `.md` files | Claude-Code-native>
   For any complex task, check the library first. If no skill fits, ask the user whether to create one before improvising.
   ```

   For Codex, put the same block in `AGENTS.md`. For Cursor, in `.cursorrules`.

4. **Mechanism D (README block — always):** append or create a `## Skills` section in `<project>/README.md`:

   ```markdown
   ## Skills

   - Library: `<library-root>`
   - Wiring: <mechanism> (e.g., "CLAUDE.md pointer" or "project-local copy under .claude/skills/")
   - Resync: <cadence or "n/a">
   - For any complex task, check the library first before improvising.
   ```

5. **Report "what changed":** list files copied, symlinks created, instruction files modified, README blocks added. Flag anything not done that was in the plan (e.g., skipped files the researcher excluded).

---

## Handoff with other skills

- `project-setup.md`: calls this protocol after step 6 of its agent instructions, passing the newly created project root and the Skills-section library path.
- `project-setup-existing.md`: calls this protocol from Phase 6 in place of inline wiring.
- `skills-library-setup.md`: returns `<library-root>` (and optionally converts a flat library into native format, which unlocks mechanisms A and B); this protocol then wires the library into the project.
- `skill-writing.md`: after a new skill is drafted and added to the library, the researcher may re-run this protocol with the active project to re-sync — relevant for mechanism A only.

## Common failure modes

- **Wrapping the library without sign-off.** The protocol converts flat `.md` files into `SKILL.md` directories silently in order to enable mechanism A. Symptom: canonical library changes, other tooling that read the flat files breaks. Recovery: revert; keep wrapping in `skills-library-setup.md` where the researcher explicitly owns the format decision.
- **Copy without resync discipline.** Mechanism A picked, library updates later, project copies silently drift. Symptom: agents in the project invoke a stale skill version. Recovery: declare a resync cadence in Phase 2 (or re-invoke this protocol whenever the library changes).
- **Symlink on Windows without Developer Mode.** Mechanism B attempted; the symlink fails or requires admin. Recovery: fall back to A; do not quietly run the harness without the wiring in place.
- **Flat-`.md` library + mechanism A without mechanism C.** Skills copied into `.claude/skills/` but Claude Code cannot auto-invoke them. Symptom: agents act as if no skills exist, even though the files are present. Recovery: add mechanism C on top, or go back to `skills-library-setup.md` and wrap the library.
- **Pointer without filesystem access.** Mechanism C set up, but the agent runs in a sandboxed environment that cannot reach `<library-root>`. Symptom: pointer references a path the agent cannot read. Recovery: fall back to A (bulk copy into the project sandbox).
- **Skipping the README block.** Researcher picks mechanism A only. Six months later the researcher moves the library or switches harnesses; the project's only reference to the library is inside a harness-specific file. Recovery: enforce universal rule 2 — the README block is always written.
- **Silent edits to harness-global config.** `~/.claude/CLAUDE.md` or `~/.claude/skills/` modified without the explicit sign-off from Phase 2. Recovery: revert; restart Phase 2 with the ask.
- **Replication package that won't reproduce.** Package ships depending on a Dropbox path only the author has. Recovery: for replication-bound projects, mechanism A (copy into the project) is the right default; mechanism C alone does not travel.

## Worked example

Active project: *With Great Powers* paper at `C:\Users\spaci\Dropbox\AI in Social Science Research\`. Harness: Claude Code. Library: `C:\Users\spaci\Dropbox\Skills\` — flat `.md` files (not Claude-Code-native format). Replication-bound (the paper's online appendix is a slice of this project).

1. **Phase 0** — both paths confirmed; `README.md` present; no `.claude/` in the project; no `~/.claude/skills/`.
2. **Phase 1** — primary harness Claude Code; library format flat; project replication-bound; single author. Harness evidence: none yet in project. Library evidence: 9 flat `.md` files.
3. **Phase 2** — the matrix row for (Claude Code, flat `.md`, replication-bound) recommends **mechanism C** (CLAUDE.md pointer) + manual copy of the subset of skills that the replication package needs (which are already in `appendix/`). Researcher approves; no harness-global changes. No wrapping. Resync cadence: n/a for C; the `appendix/` copies are managed by `project-setup.md`'s registry rules.
4. **Phase 3** —
   - **Mechanism C:** create `<project>/CLAUDE.md` with a "Skills" block naming `C:\Users\spaci\Dropbox\Skills\` and noting the flat format so agents know to read files directly rather than expect auto-invocation.
   - **Mechanism D:** append a `## Skills` section to `<project>/README.md` naming the library, the wiring, and the flat format.
   - No copies: the replication-bound copies already live in `appendix/` per the project's own workflow.
5. **Post-condition:** a fresh Claude Code instance opening the project reads `CLAUDE.md` and finds the library pointer on startup. A human reader of the README finds the same pointer through a different door. A reviewer reproducing the replication package reads `appendix/` directly; they do not need the author's Dropbox library.

Total time: about 15 minutes of researcher attention, dominated by the Phase 2 trade-off discussion.
