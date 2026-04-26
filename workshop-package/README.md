# Workshop package - Agentic AI for Social Science Research

Contents of the ZIP you downloaded for the 1-hour seminar. Open `workshop-package/` itself in Claude Code or Codex if you want the local wiring to load; the package is designed to be self-contained rather than dependent on an external skill library or a full Agentic Operating System install.

## What's inside

```text
workshop-package/
|-- README.md
|-- participant-setup.md
|-- live-demos.pdf
|-- live-demos.tex
|-- CLAUDE.md                 <- project instructions for Claude Code
|-- AGENTS.md                 <- project instructions for Codex
|-- .claude/
|   `-- skills/               <- Claude-native wrapper skills
|-- projects/
|   `-- README.md             <- exact setup guidance for participant working folders
|-- skills/
|   |-- README.md
|   |-- project-setup.md
|   |-- project-setup-existing.md
|   |-- skill-writing.md
|   |-- conceptualize.md
|   |-- operationalize.md
|   |-- validate-construct.md
|   |-- validate-criterion.md
|   |-- assess-reliability.md
|   |-- btw-welfare-check.md
|   `-- sources/
|       `-- Adcock and Collier 2001 apsr - measurement validity in social sciences.pdf
|-- toy-project-vdem/
|-- toy-project-anes/
`-- toy-project-qog/
```

## Set up one working project

Do not start by editing the shipped template folders directly if you can avoid it. For the session, make one working folder from the assets you want to use:

- **Use a provided example.** Copy one `toy-project-*` folder into `projects/`, rename it, and run `/project-setup-existing` on the copy.
- **Use your own assets.** Create a new folder in `projects/`, drop in the dataset and one or two reference papers you want to use, and run `/project-setup`.

`projects/README.md` gives the exact steps. This keeps the packaged examples intact so you can restart quickly if you want a clean rerun.

## The example projects

Each shipped toy project pairs a dataset with a latent variable that the measurement workflow will wrestle with:

- **V-Dem** - `clientelism` as a latent, expert-coded construct (cross-country).
- **ANES 2024** - `political efficacy` as a survey-based latent construct (US public opinion).
- **QoG** - `state capacity` as a latent construct with competing cross-national indicators.

Procedurally the seminar is the same across all three; the inputs differ. Pick the one closest to your field if you do not want to bring your own assets.

## Agent wiring

- **Claude Code:** `CLAUDE.md` plus the wrapper skills under `.claude/skills/`.
- **Codex:** `AGENTS.md`, which points directly to the local playbooks in `skills/`.
- **Canonical skill content:** `skills/*.md`. The Claude-native wrapper skills are thin bridges, not the source of truth.
- **No external dependency:** the package does not require your personal AI Operating System, a persona layer, or a long-lived memory stack.

## Live demos

1. **Project setup.** Use `/project-setup-existing` for a copied example folder, or `/project-setup` for a brand-new participant folder built from your own assets.
2. **Skill build.** Use `/skill-writing` to revise or rebuild `skills/operationalize.md` from the local Adcock and Collier source plus participant answers.
3. **Measurement dossier.** Compose `/conceptualize` -> `/operationalize` -> `/validate-construct` -> `/assess-reliability` on the latent variable in your working folder. Add `/validate-criterion` if you want the external-criterion step too.

## If you have not installed Claude Code yet

See `participant-setup.md` for the one-page prep sheet. You can also follow along without installing; the slides are self-contained.
