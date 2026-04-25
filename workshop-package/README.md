# Workshop package — Agentic AI for Social Science Research

Contents of the ZIP you downloaded for the 1-hour seminar. You do not need to read this in advance — the session walks through everything. This file exists as a map.

## What's inside

```
workshop-package/
├── README.md                 ← this file
├── participant-setup.md      ← the prep one-pager (what to install before the session)
├── live-demos.pdf            ← one-page step-by-step guide for the three live demos
├── live-demos.tex            ← LaTeX source for the demo guide
│
├── toy-project-vdem/         ← choose one
│   ├── outline.md
│   ├── draft.md
│   ├── data/
│   │   └── V-Dem-CY-FullOthers-v16_csv.zip   (raw; unzip to access)
│   └── lit/                  (empty — you'll add or we'll add together)
│
├── toy-project-anes/         ← or this one
│   ├── outline.md
│   ├── draft.md
│   ├── data/
│   │   ├── anes_timeseries_2024_userguidecodebook_20250808.pdf
│   │   └── DOWNLOAD.md       (ANES requires a free registration; steps inside)
│   └── lit/
│
├── toy-project-qog/          ← or this one
│   ├── outline.md
│   ├── draft.md
│   ├── data/
│   │   └── qog_std_cs_jan26.csv
│   └── lit/
│
└── skills/                   ← measurement skills (to be populated before the session)
    └── sources/              ← external sources used to build the skills
        └── Adcock and Collier 2001 apsr - measurement validity in social sciences.pdf
```

## Pick one toy project

Each toy project pairs a dataset with a *latent variable* that the workshop's measurement demo will wrestle with:

- **V-Dem** — `clientelism` as a latent, expert-coded construct (cross-country).
- **ANES 2024** — `political efficacy` as a survey-based latent construct (US public opinion).
- **QoG** — `state capacity` as a latent construct with competing cross-national indicators.

Procedurally the demo is the same across all three; the inputs differ. Pick the one closest to your field.

## Live demos we'll run on your chosen folder

1. **Retrofit.** `/project-setup-existing` adds README, implementation-roadmap, asset-registry, and interaction-log to the folder.
2. **Skill build.** `/skill-writing` drafts a new `/operationalize` skill; four companion measurement skills are in `skills/`.
3. **Measurement dossier.** Compose `/conceptualize` → `/operationalize` → `/validate-construct` → `/assess-reliability` on the latent variable. If you brought your own data + variable instead of using one of these, you'll use yours.

## If you have not installed Claude Code yet

See `participant-setup.md` for the one-page install + authenticate steps. You can also follow along without installing — the slides are self-contained.
