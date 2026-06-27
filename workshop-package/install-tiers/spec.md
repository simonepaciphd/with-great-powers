# Install-Tier Spec — May 18 Workshop AI OS Package

**Status:** Phase 0 v2 draft. Awaiting final sign-off on the four small open questions in §10. The workshop-local Phase 1–3 work can proceed once §10 closes; the GitHub-resident Phase 1–3 work is a separate, deferred session.

**Authoring persona:** `system-engineer`.
**Date:** 2026-05-05.
**Source roadmap:** `implementation-roadmap.md` § "Parallel track — May 18 workshop & AI OS install tiers".

**Changes from v1:** architecture shifts from "ship a sanitized AI OS bundle" to "ship workshop-local docs that fetch canonical assets from a public AI OS GitHub repo." Sanitization moves upstream into the public repo. Tier (a) ships four personas (`chief-of-staff`, `writer`, `engineer`, `researcher`), not one. The `project-setup` skill grows a Phase 0 fork (insulated vs. linked-to-harness) instead of splitting into two skills.

---

## 1. Purpose

Specify the file layout, content, cross-harness wiring, and install instructions for three install tiers shipped at the May 18 departmental workshop. The spec is the contract for two parallel work streams — workshop-local artifacts under this repo, and canonical assets in the public AI OS GitHub repo. Once signed, each work stream executes mechanically against this document.

## 2. Locked decisions (re-stated, not re-litigated)

1. **Sanitization stance:** scaffolding only — skeleton + minimal seed, strip private content. Sanitization happens **upstream in the public AI OS GitHub repo**, not in the workshop ZIP.
2. **Cross-harness scope:** Claude Code + Codex. Antigravity is out of scope for v1.
3. **Workshop format:** single linear track with optional sidebars.
4. **Build approach:** build tier (a) first; deconstruct into (b) and (c).
5. **Asset distribution model (new in v2):** all three tiers source their installable assets (skills, personas, identity scaffolding, agents, hooks) from a public AI OS GitHub repo. Each tier has a workshop-agnostic setup-instructions doc in that repo. The workshop-local `install-tiers/` folder contains only thin wrappers (workshop-context framing, dry-run scripts, slide cross-references) and the spec itself.
6. **`project-setup` shape:** keep two canonical skills (`project-setup.md` for new, `project-setup-existing.md` for retrofit). Each grows a Phase 0 fork — *insulated* (project carries its own copies of skills) or *linked* (project points at the user's existing AI OS / harness, which need not be Simone's). Tier (a)/(b) default to *linked*; tier (c) defaults to *insulated*.
7. **Persona naming:** sanitized personas ship under new names — `chief-of-staff`, `writer`, `engineer`, `researcher`. The current `writing` / `system-engineer` / `research` personas in the personal AI OS are being renamed in lockstep (Simone's pass).

## 3. Repo locations

### 3.1 Workshop-local (this repo)

```
workshop-package/install-tiers/
├── spec.md                  ← this file
├── full-os/                 ← tier (a) workshop-local wrapper
├── skeleton/                ← tier (b) workshop-local wrapper
└── project-only/            ← tier (c) workshop-local wrapper
```

Each tier folder under `install-tiers/` contains: a workshop-local `README.md` that points participants at the public-repo setup instructions with May-18-specific framing; a `dry-run.md` checklist for Simone to walk before the workshop; and any slide cross-references the deck consumes.

### 3.2 Public AI OS GitHub repo

Proposed layout, to be confirmed when the GitHub session lands:

```
<public AI OS repo>/
├── personal/                ← canonical sanitized AI OS structure
│   ├── CLAUDE.md
│   ├── identity/
│   ├── memory/
│   ├── personas/
│   │   ├── chief-of-staff.md
│   │   ├── writer.md
│   │   ├── engineer.md
│   │   └── researcher.md
│   ├── skills/
│   ├── agents/
│   └── home-claude/         ← contents to copy into ~/.claude/
│       ├── CLAUDE.md
│       ├── agents/
│       ├── commands/
│       ├── settings.json
│       └── scripts/
└── setup/                   ← workshop-agnostic install instructions
    ├── full-os/
    │   └── README.md        ← tier (a) install, workshop-agnostic
    ├── skeleton/
    │   └── README.md        ← tier (b) install, workshop-agnostic
    └── project-only/
        └── README.md        ← tier (c) install, workshop-agnostic
```

Optionally, `<public AI OS repo>/workshops/2026-05-18/` mirrors the workshop-local content for archival and future-runner reuse.

→ Layout details surfaced as Q1 below.

### 3.3 Two-stream work plan

| Stream                        | Where                                          | When               |
|-------------------------------|------------------------------------------------|--------------------|
| Workshop-local thin wrappers  | `workshop-package/install-tiers/`              | Phase 1–3 here     |
| Canonical sanitized AI OS     | public AI OS GitHub repo (`personal/`, `setup/`) | Deferred session  |
| Workshop-local mirror in repo | public AI OS repo `workshops/2026-05-18/`       | Deferred session  |

---

## 4. Conventions shared across tiers

### 4.1 Placeholder tokens

The sanitization pass (upstream in the GitHub repo) replaces private content with mustache-style tokens. Token vocabulary:

| Token              | Means                                                     | Used by                         |
|--------------------|-----------------------------------------------------------|---------------------------------|
| `{{NAME}}`         | Participant's full name                                   | both Claude + Codex             |
| `{{ROLE}}`         | "Lecturer in X", "Assistant Professor", "PhD candidate"   | both                            |
| `{{INSTITUTION}}`  | Affiliation                                               | both                            |
| `{{AFFILIATIONS}}` | Affiliated centers / labs                                  | both                            |
| `{{EMAIL}}`        | Primary contact email                                     | both                            |
| `{{WORK_AREAS}}`   | Bulleted research / teaching / business domains           | both                            |
| `{{INSTALL_ROOT}}` | Absolute path where the participant installs the AI OS    | both                            |
| `{{HOME_CLAUDE}}`  | `~/.claude/` (Mac) or `C:\Users\<user>\.claude\` (Win)    | Claude-only (hooks, agents, commands) |
| `{{HOME_CODEX}}`   | `~/.codex/` (Mac) or `C:\Users\<user>\.codex\` (Win)      | Codex-only — currently unused in v1; reserved for future user-global Codex config |
| `{{PROJECT_ROOT}}` | Absolute path of a participant project                    | both — used in per-project `CLAUDE.md` / `AGENTS.md` written by `project-setup` |

The public AI OS repo carries a `setup/placeholders.md` reference listing every token and where it appears.

### 4.2 What gets stripped (upstream, in the GitHub sanitization pass)

Stripped:

- All Simone-specific identifiers (name, email, institution, affiliations, headshots, CVs, `websites.txt`, body of `principles-statement.md`, `project-landscape.md`).
- All `projects-ledger.md` row content (names, slugs, collaborators, deadlines).
- All filled log entries (`chief-of-staff-log.md`, `system-engineer-log.md`, `research-log.md`, `skill-usage.log`).
- All non-template queue entries.
- `_archived/` ledger stanzas in their entirety.

Kept (sanitized, with `{{TOKEN}}`s):

- Skill files (`*-protocol.md`) — practice-encoding, not identity-encoding.
- Persona file structure and stance, for the four personas shipped.
- Folder skeleton, schemas, frontmatter shapes.
- Hooks structure in `settings.json` (paths rewritten to `{{HOME_CLAUDE}}`).

### 4.3 Cross-harness wiring strategy (general)

Claude Code and Codex have asymmetric discovery models; the strategy resolves the asymmetry without forcing the participant to think about it.

- **Claude Code reads** `~/.claude/CLAUDE.md` (user-global) and `<project>/CLAUDE.md` (per-project) automatically. Native skills at `~/.claude/skills/<name>/SKILL.md` or `<project>/.claude/skills/<name>/SKILL.md`. Subagents at `~/.claude/agents/`. Slash commands at `~/.claude/commands/`. Hooks at `~/.claude/settings.json` (+ scripts under `~/.claude/scripts/`).
- **Codex reads** `<project>/AGENTS.md` (per-project) automatically. There is no robust user-global equivalent; `~/.codex/` exists for some configurations (model selection) but not for instructions.

Three cross-harness primitives across the tiers:

1. **Shared (harness-agnostic):** plain `.md` files inside the AI OS folder. Both Claude and Codex read these as referenced content.
2. **Claude-only:** files under `.claude/` (project) or `~/.claude/` (user-global). Codex ignores them.
3. **Codex-only:** `AGENTS.md` files. Claude reads them only when explicitly told to.

Tier (a) wires Claude via `~/.claude/CLAUDE.md` and Codex via per-project `AGENTS.md` (the `project-setup` skill writes both connectors). Tier (b) wires both via the `ide-wiring` meta-skill (authored upstream in the public AI OS). Tier (c) ships both connectors at the project-folder root, matching the existing `workshop-package/` precedent.

### 4.4 Project-setup Phase 0 fork (new in v2)

Both `project-setup.md` and `project-setup-existing.md` grow a Phase 0 question: *"Is this an **insulated** project (carries its own copies of skills, no external skill-library dependency) or **linked** to your existing AI OS (skill-library pointer, harness-aware wiring)?"*

The fork affects two narrow places downstream:

| Phase                  | Insulated branch                                                        | Linked branch                                                        |
|------------------------|-------------------------------------------------------------------------|----------------------------------------------------------------------|
| Skill copying          | Copy needed `*.md` skill files into `<project>/skills/`. Write `.claude/skills/<name>/SKILL.md` wrappers per the `workshop-package/` precedent. | No copy. Write a "Skills" pointer in project `README.md` to the user's AI OS root (resolved via `skills-library-connection.md`). |
| Connector wiring       | Project-root `CLAUDE.md` and `AGENTS.md` reference local `skills/`.     | Project-root `CLAUDE.md` and `AGENTS.md` reference the user's AI OS root path. |

Tier (a)/(b) ship the skills with default = *linked*. Tier (c) ships them with default = *insulated*. Same canonical skill files; different default Phase 0 answer.

---

## 5. Tier (a) — Full sanitized AI OS

### 5.1 Entry point

Workshop participant opens `workshop-package/install-tiers/full-os/README.md`. That file points them at the canonical install instructions in the public AI OS GitHub repo (`setup/full-os/README.md`).

### 5.2 Workshop-local README template

**Length target:** 30–60 lines. Tone: thin pointer, May-18-specific framing.

**Sections:**

1. **What this tier is** (1 paragraph: the full sanitized AI OS).
2. **Why pick this tier** (2 lines).
3. **Install** (link to public-repo setup instructions; mention any May-18-specific shortcuts).
4. **What you get after install** (4 personas, full skill library, hooks, identity scaffolding).
5. **Walkthrough during the workshop** (slide §5 cross-reference; live-demo cue if any).

### 5.3 Public-repo setup README template (`setup/full-os/README.md`)

**Length target:** 200–400 lines. Tone: workshop-agnostic, release-notes voice.

**Sections:**

1. **What this is.**
2. **What's inside** (file tree from §5.4).
3. **Install — Mac** (numbered, copy-pastable shell commands).
4. **Install — Windows** (numbered, copy-pastable PowerShell commands).
5. **First-session walkthrough** (open Claude Code, observe `chief-of-staff` auto-load, run `/project-setup` in a sandbox).
6. **Filling in the placeholders** (table from §4.1).
7. **Cross-harness notes** (Claude and Codex sections).
8. **Customizing** (pointers to meta-skills).
9. **Limitations & known gaps.**

### 5.4 GitHub-resident asset inventory (tier a)

All entries below live in the public AI OS GitHub repo, sanitized at upload time (deferred session). Source paths are read-only this pass.

```
<public repo>/personal/
├── CLAUDE.md                                  ← sanitized connector layer
├── identity/
│   ├── sources/principles-statement.md        ← placeholder template
│   └── drafts/source-digest.md                ← empty template
├── memory/
│   ├── projects-ledger.md                     ← header + 1 example row
│   ├── projects-archive-ledger.md             ← header only
│   ├── projects-ledger/
│   │   ├── _template.md                       ← copied verbatim
│   │   └── example-project.md                 ← 1 worked stanza
│   ├── connector-update-queue.md              ← header only
│   ├── identity-update-queue.md               ← header only
│   ├── chief-of-staff-log.md                  ← header only
│   ├── engineer-log.md                        ← header only
│   ├── research-log.md                        ← header only
│   └── skill-usage.log                        ← empty
├── personas/
│   ├── chief-of-staff.md                      ← sanitized + renamed
│   ├── writer.md                              ← sanitized (was writing.md)
│   ├── engineer.md                            ← sanitized (was system-engineer.md)
│   └── researcher.md                          ← sanitized (was research.md)
├── skills/
│   ├── project-setup.md                       ← Phase 0 fork added (linked default)
│   ├── project-setup-existing.md              ← Phase 0 fork added (linked default)
│   ├── persona-writing-protocol.md
│   ├── skill-writing-protocol.md
│   ├── skills-library-connection.md           ← edit: write both CLAUDE.md + AGENTS.md
│   ├── skills-library-setup.md
│   ├── security-officer-protocol.md
│   ├── identity-building.md                   ← NEW (authored upstream)
│   └── ide-wiring.md                          ← NEW (authored upstream)
├── agents/
│   └── librarian.md
└── home-claude/
    ├── CLAUDE.md                              ← user-global, sanitized
    ├── agents/
    │   ├── librarian.md
    │   └── security-officer.md
    ├── commands/
    │   ├── chief-of-staff.md
    │   ├── persona.md
    │   ├── writer.md
    │   ├── engineer.md
    │   └── researcher.md
    ├── settings.json                          ← hooks; paths use {{HOME_CLAUDE}}
    └── scripts/
        └── security-officer/{check-bash,check-edit-write,check-user-prompt}.py
```

**Source-resolution table** (where each upstream-sanitized file is sourced from in Simone's working AI OS):

| Target in public repo                                            | Source (read-only)                                                                                       | Sanitization                                                                                |
|------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------|
| `personal/CLAUDE.md`                                             | `personal/CLAUDE.md`                                                                                     | Replace identity → `{{TOKEN}}`s; rewrite `C:\Users\spaci\...` → `{{INSTALL_ROOT}}\...`; strip GitHub repo names |
| `personal/identity/sources/principles-statement.md`              | `personal/identity/sources/principles-statement.md`                                                      | Replace body with placeholder template; keep heading shape                                  |
| `personal/identity/drafts/source-digest.md`                      | `personal/identity/drafts/source-digest.md`                                                              | Replace body with empty template                                                            |
| `personal/memory/projects-ledger.md`                             | `personal/memory/projects-ledger.md`                                                                     | Strip rows; keep header + 1 illustrative row                                                |
| `personal/memory/projects-archive-ledger.md`                     | same                                                                                                     | Strip rows; keep header                                                                     |
| `personal/memory/projects-ledger/_template.md`                   | same                                                                                                     | Verbatim                                                                                    |
| `personal/memory/projects-ledger/example-project.md`             | new                                                                                                      | Author from `_template.md` with fictional content                                           |
| `personal/memory/{connector-update-queue,identity-update-queue,chief-of-staff-log,engineer-log,research-log}.md` | corresponding files in `personal/memory/` (renamed `system-engineer-log.md` → `engineer-log.md`)          | Strip entries; keep headers                                                                 |
| `personal/memory/skill-usage.log`                                | same                                                                                                     | Empty                                                                                       |
| `personal/personas/chief-of-staff.md`                            | `personal/personas/chief-of-staff.md`                                                                    | Replace "Simone" → `{{NAME}}`; keep stance                                                   |
| `personal/personas/writer.md`                                    | `personal/personas/writing.md` (post-rename)                                                             | Same identity sweep; keep stance                                                            |
| `personal/personas/engineer.md`                                  | `personal/personas/system-engineer.md` (post-rename)                                                     | Same                                                                                        |
| `personal/personas/researcher.md`                                | `personal/personas/research.md` (post-rename)                                                            | Same                                                                                        |
| `personal/skills/project-setup.md`                               | `personal/skills/project-setup.md`                                                                       | Add Phase 0 insulated/linked fork; path-token sweep                                         |
| `personal/skills/project-setup-existing.md`                      | same                                                                                                     | Add Phase 0 fork; path-token sweep                                                          |
| `personal/skills/persona-writing-protocol.md`                    | same                                                                                                     | Path-token sweep                                                                            |
| `personal/skills/skill-writing-protocol.md`                      | same                                                                                                     | Path-token sweep                                                                            |
| `personal/skills/skills-library-connection.md`                   | same                                                                                                     | Edit: write both `CLAUDE.md` and `AGENTS.md` when both harnesses are present; path-token sweep |
| `personal/skills/skills-library-setup.md`                        | same                                                                                                     | Path-token sweep                                                                            |
| `personal/skills/security-officer-protocol.md`                   | same                                                                                                     | Path-token sweep                                                                            |
| `personal/skills/identity-building.md`                           | new                                                                                                      | Author upstream; mirrors Phase-0–5 shape of `persona-writing-protocol.md`                   |
| `personal/skills/ide-wiring.md`                                  | new                                                                                                      | Author upstream; walkthrough for Claude Code + Codex install + verification                 |
| `personal/agents/librarian.md`                                   | same                                                                                                     | Strip Simone-specific examples                                                              |
| `personal/home-claude/CLAUDE.md`                                 | `C:\Users\spaci\.claude\CLAUDE.md`                                                                       | Identity → `{{TOKEN}}`s                                                                     |
| `personal/home-claude/agents/{librarian,security-officer}.md`    | `C:\Users\spaci\.claude\agents\` (verify exists)                                                          | Strip Simone-specific examples                                                              |
| `personal/home-claude/commands/{chief-of-staff,persona,writer,engineer,researcher}.md` | `C:\Users\spaci\.claude\commands\` (verify exists; rename old aliases)                          | Verbatim if generic; rename per §2 #7                                                       |
| `personal/home-claude/settings.json`                             | `C:\Users\spaci\.claude\settings.json`                                                                   | Strip permissions/MCP tokens; rewrite hook paths to `{{HOME_CLAUDE}}`                       |
| `personal/home-claude/scripts/security-officer/*.py`             | `C:\Users\spaci\.claude\scripts\security-officer\`                                                       | Verbatim (assumed already generic; verify on upload)                                        |

**Skills explicitly excluded from the sanitized public AI OS** (Simone's specialty skills, kept private): `paper-writing-protocol.md`, `apsr_tables_figures_protocol.md`, `oped-writing-protocol.md`, `atlantic-ideas-writing-protocol.md`, `altac-writing-pitch-protocol.md`, `slide-writing-protocol.md`, `lit-review-protocol.md`, `lit-review-prompt-template.md`, `student-recommendation-letter-protocol.md`, `recover-session-protocol.md`, `literature-error-check-protocol.md`, `context-knowledge-extraction-agent.md`, `project-landscape-survey.md`. Listed for the spec record so the GitHub-side sanitization session doesn't accidentally pull them. → Q3 (re-confirm under v2 architecture).

### 5.5 Cross-harness wiring (tier a)

| File                                    | Claude Code | Codex            | Notes                                       |
|-----------------------------------------|-------------|------------------|---------------------------------------------|
| `home-claude/CLAUDE.md`                 | ✓ user-global | ignored        | Auto-loads every Claude session              |
| `home-claude/agents/`                   | ✓           | ignored          | Subagents available everywhere               |
| `home-claude/commands/`                 | ✓           | ignored          | Persona slash-command aliases                |
| `home-claude/settings.json`             | ✓           | ignored          | Hooks + permissions                          |
| `personal/` (referenced from CLAUDE.md) | shared      | shared           | Read by both as referenced content           |
| Per-project `CLAUDE.md` (created later) | ✓           | ignored          | Written by `project-setup` (linked default)  |
| Per-project `AGENTS.md` (created later) | ignored     | ✓                | Written by `project-setup` (linked default)  |

### 5.6 Install instructions outline (tier a, in public-repo `setup/full-os/README.md`)

**Mac:**

1. Clone (or download tarball of) the public AI OS GitHub repo to the chosen install root.
2. Backup existing `~/.claude/` if present.
3. Copy `personal/home-claude/` contents into `~/.claude/`.
4. Edit `~/.claude/CLAUDE.md` and `personal/CLAUDE.md`: replace `{{TOKEN}}`s with own values.
5. Confirm Python is available (security-officer hooks).
6. Open Claude Code; observe `chief-of-staff` auto-load.
7. Optional: install Codex CLI; verify `AGENTS.md` discovery in a sandbox project.

**Windows:** parallel; `~/.claude/` resolves to `C:\Users\<user>\.claude\`; PowerShell commands provided.

---

## 6. Tier (b) — Skeleton (meta-skills bundle)

### 6.1 (b) vs (a) — what's actually different

Tier (a) ships **scaffold + minimal seed** — folder structure + four personas + populated CLAUDE.md + 1 example ledger row. The participant adapts.

Tier (b) ships **scaffold + meta-skills only — no personas, no example ledger row, no populated CLAUDE.md**. The participant's first three tasks are: `/identity-building` to fill `~/.claude/CLAUDE.md`; `/persona-writing` to draft their first persona; `/skill-writing` (or `/project-setup`) to seed their library. They build their OS into existence.

| Component                                     | Tier (a)                                       | Tier (b)                                |
|-----------------------------------------------|------------------------------------------------|-----------------------------------------|
| `personal/personas/{chief-of-staff,writer,engineer,researcher}.md` | ✓ all four shipped                  | ✗ empty `personas/` folder              |
| `personal/memory/projects-ledger.md`          | header + 1 example row                          | header only                             |
| `personal/memory/projects-ledger/example-project.md` | ✓ worked example                          | ✗ absent                                |
| `personal/memory/{chief-of-staff,engineer,research}-log.md` | headers                          | ✗ absent (no personas, no logs)         |
| `personal/CLAUDE.md`                          | sanitized + populated                            | template-only with `{{TOKEN}}`s; first-task pointer to `/identity-building` |
| `home-claude/CLAUDE.md`                       | sanitized + populated                            | template-only                           |
| `home-claude/commands/{chief-of-staff,writer,engineer,researcher}.md` | ✓ shipped                  | ✗ absent (no personas to invoke)        |
| `home-claude/agents/security-officer.md`      | ✓ shipped                                       | ✓ shipped (structural, not seeded)      |
| **Meta-skills:**                              |                                                  |                                         |
| `skills/project-setup.md`                     | ✓                                               | ✓                                       |
| `skills/project-setup-existing.md`            | ✓                                               | ✓                                       |
| `skills/persona-writing-protocol.md`          | ✓                                               | ✓                                       |
| `skills/skill-writing-protocol.md`            | ✓                                               | ✓                                       |
| `skills/skills-library-setup.md`              | ✓                                               | ✓                                       |
| `skills/skills-library-connection.md`         | ✓                                               | ✓                                       |
| `skills/security-officer-protocol.md`         | ✓                                               | ✓ (per locked decision: ships in public repo, available across tiers) |
| `skills/identity-building.md`                 | ✓ (available, optional)                          | ✓ **first-task entry point**            |
| `skills/ide-wiring.md`                        | ✓ (available, optional)                          | ✓ **available for harness reconfig**     |

### 6.2 Entry point

Workshop participant opens `workshop-package/install-tiers/skeleton/README.md`. That file points at `<public repo>/setup/skeleton/README.md` for the workshop-agnostic install steps.

### 6.3 Workshop-local README template

**Length target:** 30–60 lines. Same shape as tier (a) wrapper, with first-three-tasks panel.

### 6.4 Public-repo setup README template (`setup/skeleton/README.md`)

**Length target:** 150–250 lines. Tone: tutorial, slightly more pedagogical than tier (a)'s release-notes voice.

**Sections:**

1. **What this is** (1 paragraph).
2. **(b) vs (a) decision aid.**
3. **What's inside** (file tree).
4. **Install — Mac** / **Install — Windows.**
5. **First three tasks** (`/identity-building` → `/persona-writing` → `/skill-writing` or `/project-setup`).
6. **Filling in the placeholders.**
7. **What you do NOT get out-of-the-box** (no persona, no example ledger, no skill seed — and this is intentional).

### 6.5 GitHub-resident asset inventory (tier b)

The same files as tier (a)'s public-repo inventory in §5.4, with the following differences:

- `personal/personas/` — empty (no persona files shipped).
- `personal/memory/projects-ledger.md` — header only, no example row.
- `personal/memory/projects-ledger/example-project.md` — absent.
- `personal/memory/{chief-of-staff,engineer,research}-log.md` — absent.
- `personal/CLAUDE.md` — template-only.
- `personal/home-claude/CLAUDE.md` — template-only.
- `personal/home-claude/commands/` — empty (no persona aliases).

All meta-skills, `security-officer-protocol.md`, and `home-claude/agents/security-officer.md` ship as in tier (a).

### 6.6 Install instructions outline (tier b)

Steps 1–4 identical to tier (a). Step 5 onward is *"open Claude Code, run `/identity-building`, then `/persona-writing`, then `/skill-writing` to seed your library, then `/project-setup` for your first project."*

---

## 7. Tier (c) — Project-only

### 7.1 Entry point

Workshop participant opens `workshop-package/install-tiers/project-only/README.md`. That file points at `<public repo>/setup/project-only/README.md`. The installable artifact in that repo is a self-contained folder the participant downloads (or clones a `<public repo>/setup/project-only/template/` subdirectory) and renames as their project.

### 7.2 Workshop-local README template

**Length target:** 30–60 lines.

### 7.3 Public-repo setup README template (`setup/project-only/README.md`)

**Length target:** 80–150 lines. Tone: matches existing `workshop-package/README.md` — terse, mechanical, single-page-printable.

**Sections:**

1. **What this is** (one paragraph: a single-folder drop with `project-setup` and `project-setup-existing`, defaulted to *insulated*).
2. **What it isn't** (no persona, no skill library, no identity layer — those are tiers a and b).
3. **Install** (download the template folder, rename, open).
4. **First task** (`/project-setup` for new, `/project-setup-existing` for existing).
5. **What ships inside** (file tree).
6. **Cross-harness notes.**

### 7.4 GitHub-resident asset inventory (tier c)

Layout of the downloadable template (`<public repo>/setup/project-only/template/`):

```
template/
├── README.md                          ← workshop-agnostic
├── CLAUDE.md                          ← project instructions for Claude Code
├── AGENTS.md                          ← project instructions for Codex
├── skills/
│   ├── project-setup.md               ← canonical, default fork = insulated
│   └── project-setup-existing.md      ← canonical, default fork = insulated
└── .claude/
    └── skills/
        ├── project-setup/
        │   └── SKILL.md               ← Claude-native wrapper
        └── project-setup-existing/
            └── SKILL.md               ← Claude-native wrapper
```

**Precedent:** matches the existing `workshop-package/.claude/skills/project-setup/SKILL.md` wiring pattern verbatim.

### 7.5 Cross-harness wiring (tier c)

| File                                   | Claude Code | Codex   | Notes                                       |
|----------------------------------------|-------------|---------|---------------------------------------------|
| `CLAUDE.md`                            | ✓           | ignored | Project-level Claude instructions           |
| `AGENTS.md`                            | ignored     | ✓       | Project-level Codex instructions            |
| `skills/*.md`                          | shared      | shared  | Canonical playbooks                         |
| `.claude/skills/*/SKILL.md`            | ✓           | ignored | Claude-native wrappers                      |

This is the existing `workshop-package/` pattern minus the toy projects, minus the measurement skills, plus a slimmer README.

### 7.6 Install instructions outline (tier c)

1. Download / clone the `template/` folder from the public repo.
2. Move and rename it as your project folder.
3. Open in Claude Code or Codex.
4. Run `/project-setup` (new) or `/project-setup-existing` (existing). Phase 0 will default to *insulated*.

No `~/.claude/` modification. No identity layer. No hooks.

---

## 8. Cross-harness summary (all tiers)

| Tier | Claude-only files                                              | Codex-only files                          | Shared files                              |
|------|----------------------------------------------------------------|-------------------------------------------|-------------------------------------------|
| (a)  | `home-claude/*`; per-project `CLAUDE.md` (written by `project-setup`) | per-project `AGENTS.md` (written by `project-setup`) | `personal/*` (CLAUDE.md, identity, memory, personas, skills, agents) |
| (b)  | `home-claude/CLAUDE.md`, `home-claude/agents/security-officer.md`, `home-claude/settings.json`, `home-claude/scripts/`; per-project `CLAUDE.md` (after `ide-wiring`) | per-project `AGENTS.md` (after `ide-wiring`) | `personal/*` (skills only; no personas, empty memory) |
| (c)  | `CLAUDE.md`, `.claude/skills/*/SKILL.md`                       | `AGENTS.md`                               | `skills/*.md`                             |

---

## 9. Phase 1–3 execution checklist

The original roadmap's Phase 1–3 splits into two streams under v2.

### 9.1 Workshop-local stream (this repo, this workshop window)

1. Author `workshop-package/install-tiers/full-os/README.md` (thin wrapper per §5.2).
2. Author `workshop-package/install-tiers/skeleton/README.md` (thin wrapper per §6.3).
3. Author `workshop-package/install-tiers/project-only/README.md` (thin wrapper per §7.2).
4. Author `dry-run.md` per tier (Simone's pre-workshop walk-through checklist).
5. Author slide cross-references (deck §5 will link tier names to setup-README anchors).
6. Stage placeholder URLs in the workshop-local READMEs; update once GitHub repo lands.

### 9.2 GitHub-resident stream (deferred to a separate session)

1. Stand up / extend the public AI OS GitHub repo per §3.2.
2. Sanitize and push `personal/` contents per §5.4 source-resolution table.
3. Author the two new meta-skills (`identity-building.md`, `ide-wiring.md`) into `personal/skills/`.
4. Edit `personal/skills/skills-library-connection.md` to write both `CLAUDE.md` and `AGENTS.md` when both harnesses are likely.
5. Edit `personal/skills/project-setup.md` and `project-setup-existing.md` to add Phase 0 insulated/linked fork.
6. Author `setup/full-os/README.md`, `setup/skeleton/README.md`, `setup/project-only/README.md` (workshop-agnostic install instructions).
7. Stage `setup/project-only/template/` per §7.4.
8. Sanitization grep pass: `grep -r "Simone\|spaci@stanford\|Stanford\|CDDRL"` against the public repo; expect 0 matches.
9. Mirror the workshop-local content under `<public repo>/workshops/2026-05-18/` (optional).

### 9.3 Cross-stream validation (Phase 7 dry run)

- Each tier installable into a sandbox folder; public-repo README followed verbatim.
- Tier (a): `chief-of-staff` auto-loads in Claude; `/project-setup` runs (linked default) in a test project; security-officer hook fires on a sentinel.
- Tier (b): `/identity-building` runs and produces a populated `~/.claude/CLAUDE.md`; `/persona-writing` runs and produces a persona file.
- Tier (c): `/project-setup` runs in a test sandbox (insulated default); `AGENTS.md` discovered by Codex.

---

## 10. Open questions for Simone

Closed in this round (locked into spec): repo location; identity-building skill authoring; ide-wiring skill authoring; GitHub-linked architecture; codex-token parity; four-persona ship; persona renames; project-setup Phase 0 fork; security-officer in public repo; tier-a excluded skills.

Still open:

1. **Public AI OS GitHub layout (§3.2).** I propose `personal/` for canonical AI OS + `setup/<tier>/` for install instructions, optionally `workshops/2026-05-18/` for archival. If the existing `skills-public` repo (referenced in `personal/CLAUDE.md`) has a different shape, name it. Single repo or multi-repo?

2. **Workshop-local thin wrapper detail (§3.1, §5.1, §6.2, §7.1).** Plan ships a `README.md` + `dry-run.md` per tier under `workshop-package/install-tiers/<tier>/`. Anything else workshop-local you want — e.g., a `tier-decision-tree.md` for slide §5 cross-reference, or per-tier post-workshop participant cheat-sheets?

3. **Excluded private skills re-confirm under v2 architecture (§5.4 cut list).** Same 13 skills as v1's exclusion list. Under the GitHub-linked model these are private to your personal AI OS and don't ship in the public repo. Confirm the cut, or are any borderline?

4. **Deck §5 (10-min "three tiers + when to pick each").** Need a one-pager `tier-decision-tree.md` as a slide source? Or keep slide content in Overleaf only, with the workshop-local wrappers as the install pointer?

---

**Stop.** Once §10 closes, the workshop-local stream (§9.1) can execute in this session or the next; the GitHub-resident stream (§9.2) is a separate session as you noted.
