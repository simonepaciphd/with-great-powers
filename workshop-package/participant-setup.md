# Agentic AI for Social Science Research - Participant Prep

**What this is.** A one-hour hybrid seminar: a short paper presentation on how to use agentic AI responsibly in research, threaded with three live demos you can code along with. Two governing principles anchor the argument: **researcher control** and **radical transparency**.

**What you'll walk away with.**

- The five-layer setup stack for agentic research workflows (tool -> harness -> context -> prompt -> management).
- A self-contained seminar package with local Claude/Codex wiring instead of a full external OS dependency.
- Five measurement skills plus two setup/meta-skills you can reuse after the session.
- A worked measurement dossier on a latent variable, either yours or one of ours.

## To code along, prep before the session

1. **Install Claude Code.** Five minutes, platform-specific instructions at [https://claude.ai/code](https://claude.ai/code).
2. **Authenticate.** You'll need an Anthropic account; trial credits cover the session.
3. **Download the workshop package** from the Dropbox link: [https://www.dropbox.com/scl/fo/ryawd2w14s41zr604qdeo/ABu8y9wszGLw0Rijn9dXWSo?rlkey=savschqff9i3cfrjcx04vcblg&st=q4mx89nc&dl=1](https://www.dropbox.com/scl/fo/ryawd2w14s41zr604qdeo/ABu8y9wszGLw0Rijn9dXWSo?rlkey=savschqff9i3cfrjcx04vcblg&st=q4mx89nc&dl=1). The ZIP downloads automatically; unzip it wherever you keep research projects.
4. **Open `workshop-package/` itself in Claude Code or Codex.** Do not open only a toy-project subfolder if you want the local package wiring to load.

## Exact setup for the live session

Create exactly **one working folder** for the seminar before we start the demos. Use `workshop-package/projects/` as the staging area.

**Option A - use one of our examples.**

1. Copy one folder from `toy-project-vdem/`, `toy-project-anes/`, or `toy-project-qog/` into `projects/`.
2. Rename the copy to something you will recognize during the session.
3. During Demo 1, run `/project-setup-existing` on that copied folder.

**Option B - use your own assets.**

1. Create a new folder inside `projects/`.
2. Put your dataset (or a manageable slice of it) in that folder. If you already have one or two reference papers on the concept, put them there too.
3. During Demo 1, run `/project-setup` on that folder.

The package includes local wiring for Claude Code (`CLAUDE.md` plus `.claude/skills/`) and Codex (`AGENTS.md`). You do **not** need a full external Agentic Operating System install for the seminar package to work.

## Data: bring your own, or use ours

**Option A - bring your own.** Pick one concept from your current research that you have struggled to measure directly - something latent. Examples: civic engagement, clientelism, state capacity, democratic backsliding, institutional trust, political efficacy. Bring:

- a dataset (or a slice of one) containing candidate indicators;
- one or two papers on how the concept has been measured in prior work.

**Option B - use one of our toy projects.** The package ships three; pick the one closest to your field.

- **V-Dem v16 + clientelism index** - cross-country, expert-coded latent measure.
- **ANES 2024 + political efficacy** - US public opinion, classic survey-based construct. ANES requires a free registration to download the data; instructions are in the folder.
- **QoG standard cross-section + state capacity** - cross-country composite, multiple competing measures.

## Two questions to think about beforehand

1. What is one concept in your research you have struggled to measure?
2. What validity threat have you worried about and not fully resolved?

## Format

Sixty minutes, integrated Q&A - interrupt whenever rather than saving it for the end. Three live demos of about five minutes each. The slide deck and the package contents are yours to keep.

---

**Questions before the session:** spaci@stanford.edu
