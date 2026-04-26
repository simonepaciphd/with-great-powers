---
name: project-setup-existing
description: Retrofits a copied toy project or other pre-existing participant folder with lightweight provenance scaffolding while preserving the existing layout as much as possible.
---

# /project-setup-existing - retrofit a working folder without overhauling it

This skill is for folders that already contain materials: a copied toy project, a participant folder with notes already inside it, or any other pre-existing workshop folder that needs provenance scaffolding added around the edges.

## When to use

- The participant copied one of the shipped `toy-project-*` folders into `projects/`.
- The participant already has a folder with data, draft text, or notes in place.
- The goal is to preserve the current layout and add the seminar workflow around it.

## Do not use when

- The folder is brand new or effectively empty. Use `/project-setup`.
- The user wants a full restructure of an entire research archive. This workshop version is intentionally minimal.

## The retrofit

1. **Confirm the target folder.** Work on exactly one participant folder at a time.
2. **Inventory first.** List the files and folders already present before proposing moves.
3. **Default to minimal adoption.** Keep the participant's existing layout unless a move is obviously useful and explicitly approved.
4. **Create the missing scaffold.** Add `README.md`, `implementation-roadmap.md`, `asset-registry.csv`, `interaction-log.csv`, and any missing `docs/` or `archive/` folders.
5. **Preserve the existing assets.** Keep copied toy-project materials such as `outline.md`, `draft.md`, `data/`, and `lit/` in place unless the participant asks otherwise.
6. **Write `README.md`.** Include project purpose, latent concept, data note, folder map, and a Skills section pointing back to `../skills/`.
7. **Write `implementation-roadmap.md`.** Keep the same short workshop checklist: setup, conceptualize, operationalize, validate construct, validate criterion (optional), assess reliability, synthesis.
8. **Create `asset-registry.csv`.** Use the header:

```csv
asset_path,asset_type,creator,model_metadata,created,last_modified,verification,notes
```

9. **Backfill the asset registry conservatively.** Register every pre-existing asset the participant expects to use. Default `verification` to `not-verified` unless the participant has just reviewed the file.
10. **Create and seed `interaction-log.csv`.** Use the standard header and log the retrofit session itself.

## Failure modes

- **Over-cleaning.** The agent treats a copied example as something to reorganize heavily. Preserve the example's layout unless asked.
- **No checkpoint before moves.** The agent starts moving files without confirming. Inventory first, then ask.
- **Registry drift.** New scaffold files are created but the original contents are not registered. Backfill immediately.
- **External-library dependence.** The agent assumes a global skill library. Use the local package skills only.

## Output

Produce a retrofitted folder that keeps the original materials in place while adding:

- `README.md`
- `implementation-roadmap.md`
- `asset-registry.csv`
- `interaction-log.csv`
- `docs/` and `archive/` if missing

## Handoff

After `/project-setup-existing`, the next step is usually `/conceptualize`. If the participant decides to start over with a fresh empty folder, use `/project-setup` instead.

## Explicit non-claims

This skill does not decide the substantive research direction and does not authorize large restructures by default. It adds workshop scaffolding around an existing folder.
