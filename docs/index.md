---
layout: default
title: With Great Powers
---

<div class="lede">
  <p><strong>Agentic AI is already reshaping social-science workflows.</strong> Adoption has outpaced shared standards, risking uneven uptake and a widening replicability gap. This paper is a practical manual for using agentic AI effectively <em>and</em> responsibly — grounded in two principles and a five-layer setup that researchers can implement today.</p>

  <p class="cta">
    <a class="btn btn-primary" href="https://www.dropbox.com/scl/fo/fhwo1steehsz9knhxkjmt/AKRke9Y-8cThLowew2Gw_Bs?rlkey=i7etn98de7zvv0m5dej4amqg3&st=gx0ysnm1&dl=0" target="_blank" rel="noopener">📄 Read the current draft</a>
    <a class="btn" href="https://github.com/simonepaciphd/with-great-powers" target="_blank" rel="noopener">💾 Replication package</a>
  </p>
</div>

<figure class="hero-figure">
  <img src="{{ '/assets/images/two-extremes.png' | relative_url }}" alt="Side-by-side infographic contrasting black-box delegation with substantive control and radical transparency in AI-assisted research.">
  <figcaption>Two extremes of AI-assisted research — from black-box delegation to substantive control with radical transparency.</figcaption>
</figure>

## Two governing principles

<div class="principles">
  <div class="principle">
    <h3>Researcher control</h3>
    <p>Every substantive decision — framing, empirical design, interpretation, final phrasing — stays with the researcher. Execution may be delegated; ownership and judgment cannot.</p>
  </div>
  <div class="principle">
    <h3>Radical transparency</h3>
    <p>A credible replication package must now extend to the <em>inputs, throughputs, and outputs</em> of the AI-assisted process itself — not just data and code.</p>
  </div>
</div>

## The setup stack

The paper proposes a five-layer workflow. Each layer conditions the ones below it — tool choice determines which harnesses can exist on top; the harness determines which skills and tools the agent can reach; and so on down to agent-level management across the research process.

<div class="stack">
  <div class="stack-step"><span class="num">1</span><div><strong>Tool choice</strong><span class="sub">GenAI model + IDE/harness</span></div></div>
  <div class="arrow">↓</div>
  <div class="stack-step"><span class="num">2</span><div><strong>Harness engineering</strong><span class="sub">tools, skills, permissions, control loops</span></div></div>
  <div class="arrow">↓</div>
  <div class="stack-step"><span class="num">3</span><div><strong>Context engineering</strong><span class="sub">project folder as sandbox repository</span></div></div>
  <div class="arrow">↓</div>
  <div class="stack-step"><span class="num">4</span><div><strong>Prompt engineering</strong><span class="sub">precise, goal-oriented instructions</span></div></div>
  <div class="arrow">↓</div>
  <div class="stack-step"><span class="num">5</span><div><strong>Agent management</strong><span class="sub">orchestration + verification across the research process</span></div></div>
</div>

<p class="fig-caption">Figure 1 · Setting up AI agents in the research process.</p>

## Skills as the central artifact

Inside any harness, the highest-leverage object is the **skill library**: a persistent, personal repository of reusable procedures an agent can invoke on demand. Skills transcend any single project and should be built through a disciplined procedure combining external sources with the researcher's own tacit knowledge.

<div class="skill-diagram">
  <div class="row">
    <div class="node">
      <strong>External sources</strong>
      <span class="sub">scientific literature, trusted templates</span>
    </div>
    <div class="node">
      <strong>Own sources</strong>
      <span class="sub">prior work samples, self-interview</span>
    </div>
  </div>
  <div class="arrows">↘ &nbsp;&nbsp;&nbsp; ↙</div>
  <div class="node center highlight">
    <strong>Skill</strong>
    <span class="sub">reusable, named procedure</span>
  </div>
  <div class="arrows">↓</div>
  <div class="node center">
    <strong>Performance review</strong>
    <span class="sub">where the skill fell short in use</span>
  </div>
  <div class="feedback">↑ feedback loops back to sources</div>
</div>

<p class="fig-caption">Figure 2 · A procedural approach to skill-building.</p>

## Where agents fit across the research process

Every stage of a research project offers candidate applications for delegation. The general rule: weight the balance between the **procedural** and **substantive** nature of a task — agents shine on procedural work, become unreliable when decisions turn substantive.

<div class="stages">
  <div class="stage">
    <h4>Question</h4>
    <p>scope literatures; surface adjacent work; stress-test framings</p>
  </div>
  <div class="arrow-h">→</div>
  <div class="stage">
    <h4>Theory</h4>
    <p>trace implications of assumptions; generate derivations; catch inconsistencies</p>
  </div>
  <div class="arrow-h">→</div>
  <div class="stage">
    <h4>Empirics</h4>
    <p>implement pipelines; run specification sweeps; produce tables and figures</p>
  </div>
  <div class="arrow-h">→</div>
  <div class="stage">
    <h4>Writing</h4>
    <p>draft, edit, compress; convert across formats; prepare slides</p>
  </div>
</div>

<p class="fig-caption">Figure 4 · Research stages and candidate agentic AI applications.</p>

## Radical transparency in practice

Context engineering treats each project as a sandbox repository — a single folder carrying every piece of knowledge the agent needs: background concepts, literature, data, scripts, feedback. Every asset in the folder is flagged for provenance (`human` / `agent` / `mixed`) and verification (`not-verified` / `partially-verified` / `human-verified`). Every non-trivial agent session is logged. The result is a replication package that documents the AI's role, not just the final code.

<div class="tree-and-workflows">
<pre class="tree">
project/
  README.md
  implementation-roadmap.md
  asset-registry.csv
  interaction-log.csv
  background/
    literature/
    concepts/
    feedback/
    archive/
  drafts/
  data/
  figures/
  tables/
  scripts/
  appendix/
</pre>

<ul class="workflows">
  <li><strong>Verification flags</strong> on every major asset: <code>not-verified</code>, <code>partially-verified</code>, <code>human-verified</code>.</li>
  <li><strong>Provenance flags</strong>: <code>human</code>, <code>agent</code>, or <code>mixed</code> for each asset entry.</li>
  <li><strong>Interaction log</strong> summarizing every non-trivial agent session (date, input, output, model metadata).</li>
  <li><strong>Archive pattern</strong>: obsolete files move to a local <code>archive/</code> rather than being deleted.</li>
  <li><strong>Project-setup skill</strong> scaffolds the above structure in a single invocation.</li>
</ul>
</div>

<p class="fig-caption">Figure 3 · A sample project context setup.</p>

## What's in the replication package

This site's companion repository <em>is</em> the project folder used to write the paper — released as a working replication package so readers can inspect every artifact, its provenance, and the full interaction history.

<div class="assets">
  <div class="asset">
    <h4><code>appendix/</code></h4>
    <p>Online appendix. Every asset cited in the main text, including the dogfooded skills: <code>project-setup</code>, <code>skill-writing</code>, <code>lit-review-protocol</code>, <code>skills-library-setup</code>, <code>startup-checklist</code>.</p>
  </div>
  <div class="asset">
    <h4><code>drafts/</code></h4>
    <p>Paper drafts, including the agent-produced first draft and the latest compiled PDF.</p>
  </div>
  <div class="asset">
    <h4><code>background/</code></h4>
    <p>Literature notes, concepts, feedback. <code>background/literature/</code> is Zotero-compatible BibTeX with per-source classification.</p>
  </div>
  <div class="asset">
    <h4><code>figures/</code>, <code>tables/</code>, <code>scripts/</code></h4>
    <p>Figures, tables, and demo code referenced in the paper.</p>
  </div>
  <div class="asset">
    <h4><code>asset-registry.csv</code></h4>
    <p>Every artifact with provenance flag (<code>human</code> / <code>agent</code> / <code>mixed</code>) and verification status.</p>
  </div>
  <div class="asset">
    <h4><code>interaction-log.csv</code></h4>
    <p>Every non-trivial AI-assisted session from inception through final draft.</p>
  </div>
  <div class="asset">
    <h4><code>AGENTS.md</code></h4>
    <p>Rules-of-engagement for AI agents in this folder. Dogfoods the paper's own control / transparency principles.</p>
  </div>
  <div class="asset">
    <h4><code>implementation-roadmap.md</code></h4>
    <p>Living to-do list used during writing — the entry point for any new agent session.</p>
  </div>
</div>

## Citation

> Paci, Simone (2026). *With Great Powers: A Practical Guide to Agentic AI for Social Science Research.* Working paper. Replication package: [github.com/simonepaciphd/with-great-powers](https://github.com/simonepaciphd/with-great-powers)

## Contact

Simone Paci · Stanford University · [spaci@stanford.edu](mailto:spaci@stanford.edu)
