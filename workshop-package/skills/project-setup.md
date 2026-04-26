---
name: project-setup
description: Scaffolds a brand-new workshop project from participant-chosen assets. Creates a lightweight research folder with provenance ledgers and a README that points back to the local seminar skills.
---

# /project-setup - start a workshop project from chosen assets

This skill is for the "bring your own data" path in the seminar. The participant has picked the assets they want to use and needs a clean local project folder before the measurement workflow begins.

## When to use

- The participant created a new folder in `projects/`.
- The folder is empty or contains only raw assets.
- The goal is to add minimal research scaffolding around those assets.

## Do not use when

- The folder already contains a copied toy project, notes, or draft materials. Use `/project-setup-existing`.
- The user wants a full lab Operating System or a global skill-library install. This workshop package is intentionally local and lightweight.

## The setup

1. **Confirm the target.** Ask for the folder path, project name, latent concept, and which assets are in scope for this session.
2. **Inventory before moving.** If files are loose at the folder root, ask before moving them into `data/` or `lit/`.
3. **Create the minimal structure.** Add any missing `data/`, `lit/`, `docs/`, and `archive/` folders.
4. **Write `README.md`.** Include the project name, research question, chosen concept, data note, a short folder map, and a Skills section pointing back to `../skills/`.
5. **Write `implementation-roadmap.md`.** Keep it short: setup, conceptualize, operationalize, validate construct, validate criterion (optional), assess reliability, synthesis.
6. **Create `asset-registry.csv`.** Use the header:

```csv
asset_path,asset_type,creator,model_metadata,created,last_modified,verification,notes
```

7. **Seed the asset registry.** Add one row for every pre-existing asset in the folder. Use conservative defaults: `verification = not-verified` unless the participant says otherwise.
8. **Create `interaction-log.csv`.** Use the header:

```csv
date,session_id,harness,model,researcher_input_summary,agent_output_summary,assets_affected,notes
```

9. **Log the setup session.** Append the current setup pass to `interaction-log.csv`.
10. **Report what changed.** Summarize what was created, what was moved, and what still needs participant sign-off.

## Failure modes

- **Premature restructuring.** The agent renames or reorganizes assets before the participant confirms. Ask first.
- **Missing provenance.** The scaffold is created but the pre-existing files are not registered. Seed the registry immediately.
- **External dependency creep.** The agent points to a global skill library or memory stack. Keep everything local to the package.
- **Overbuilt template.** The agent creates a full lab OS instead of a seminar-ready working folder. Keep the setup minimal.

## Output

Produce a working project folder that contains:

- `README.md`
- `implementation-roadmap.md`
- `asset-registry.csv`
- `interaction-log.csv`
- `data/`, `lit/`, `docs/`, and `archive/` as needed

## Handoff

After `/project-setup`, the next step is usually `/conceptualize`. If the participant decides to start from a copied example instead of a fresh folder, switch to `/project-setup-existing`.

## Explicit non-claims

This skill does not decide the research question or the measurement strategy. It only creates a clean local workspace around the participant's chosen assets.
