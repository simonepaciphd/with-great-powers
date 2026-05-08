---
layout: default
title: Workshop Prep
permalink: /seminar/
---

<p class="breadcrumb"><a href="{{ '/' | relative_url }}">← Back to the paper</a></p>

<div class="lede">
  <p><strong>A one-hour hybrid seminar on the paper.</strong> A short presentation on agentic AI in social-science research, threaded with three live demos you can code along with. Two principles anchor the argument: <strong>researcher control</strong> and <strong>radical transparency</strong>.</p>

  <p class="cta">
    <a class="btn btn-primary" href="https://www.dropbox.com/scl/fo/ryawd2w14s41zr604qdeo/ABu8y9wszGLw0Rijn9dXWSo?rlkey=savschqff9i3cfrjcx04vcblg&st=q4mx89nc&dl=1">⬇ Download the workshop package (ZIP)</a>
    <a class="btn" href="https://claude.ai/code" target="_blank" rel="noopener">⚙ Install Claude Code</a>
  </p>
</div>

## What you'll walk away with

- The five-layer setup stack for agentic research workflows (tool -> harness -> context -> prompt -> management).
- A self-contained seminar package with local Claude/Codex wiring instead of a full external OS dependency.
- Five measurement skills plus two setup/meta-skills you can reuse in your own projects.
- A worked measurement dossier on a latent variable, either yours or one of ours.
- A one-page startup checklist for your next AI-assisted project.

## Setup

After installing Claude Code, authenticate with your Anthropic account - trial credits cover the session. Unzip the workshop package wherever you keep research projects, then open `workshop-package/` itself in Claude Code or Codex so the local wiring loads.

Before the session, create exactly one working folder under `workshop-package/projects/`:

- **If you want a provided example:** copy one `toy-project-*` folder into `projects/`, rename it, and use `/project-setup-existing` during Demo 1.
- **If you want your own assets:** create a new folder in `projects/`, drop in your dataset plus one or two reference papers, and use `/project-setup` during Demo 1.

The package ships with local `CLAUDE.md`, `AGENTS.md`, and Claude-native wrapper skills, so it does not depend on a separate personal AI Operating System install.

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

## After the seminar

The workshop package is self-contained. If you want to keep building after the session — composing your own skills, layering personas, wiring multiple projects — the public scaffolding behind Simone's personal AI OS is open-sourced as a starter library at [github.com/simonepaciphd/ai-os-public](https://github.com/simonepaciphd/ai-os-public). It ships the five personas (`chief-of-staff`, `researcher`, `writer`, `engineer`, `teacher`), protocol skills, and a `librarian` subagent. Methodology to fork and customize, not a turnkey product.

---

**Questions before the session:** [spaci@stanford.edu](mailto:spaci@stanford.edu)
