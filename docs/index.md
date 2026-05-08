---
layout: default
title: With Great Powers
---

<div class="lede">
  <p><strong>Agentic AI is leading a research revolution.</strong> Most social scientists have already integrated AI in their workflows, through individual experimentation and the grapevine of department corridors. However, uneven and heterogeneous uptake poses significant risks to individual researchers as well as to the whole of the research enterprise. This paper+website+repository is at once a practical manual for using agentic AI effectively and responsibly as well as a conversation-starter for thinking about the next chapter of research in the social sciences.</p>

  <p class="cta">
    <a class="btn btn-primary" href="https://www.overleaf.com/read/jxrvrtpysfsd#604ca2" target="_blank" rel="noopener">📄 Read the current draft</a>
    <a class="btn" href="https://github.com/simonepaciphd/with-great-powers" target="_blank" rel="noopener">💾 Replication package</a>
    <a class="btn" href="https://github.com/simonepaciphd/ai-os-public" target="_blank" rel="noopener">🧰 AI OS starter library</a>
    <a class="btn" href="{{ '/seminar/' | relative_url }}">🎤 Workshop Prep</a>
  </p>
</div>

## We need best practices and shared norms

Adoption has outrun shared practice and norms. Agentic AI raises two distinct questions for the research community.

<div class="principles">
  <div class="principle">
    <h3>How to reduce AI error?</h3>
    <p><em>Using AI effectively while reducing error.</em> Every new method comes with new failure modes, and the familiar task is to learn them, build the routines that catch them, and codify what works. The paper's first half lays out a five-layer workflow stack — tool, harness, context, prompt, agent management — that does exactly this.</p>
  </div>
  <div class="principle">
    <h3>How to retain control?</h3>
    <p><em>Using AI responsibly and transparently.</em> This is genuinely new. Agentic AI is the first methodology that takes <em>agency</em> in the research process — drafting, executing, deciding. It shapes not just the <em>error rate</em> of findings but the <em>direction</em> of research itself. That demands norms the field does not yet have. The paper's second half — <em>Governance</em> — proposes two: <em>researcher control</em> over every substantive decision, and <em>radical transparency</em> over the AI-assisted process.</p>
  </div>
</div>

<figure class="hero-figure">
  <img src="{{ '/assets/images/good-bad-practices.png' | relative_url }}" alt="Side-by-side simplified infographic contrasting bad and good practice in AI-assisted research.">
  <figcaption>Bad vs. good practice in AI-assisted research — from black-box delegation to disciplined control with transparency.</figcaption>
  <p class="fig-cta"><a class="btn-fig" href="#fig-two-extremes-detail">View detailed infographic</a></p>
</figure>

<div id="fig-two-extremes-detail" class="lightbox" aria-hidden="true">
  <a href="#!" class="lightbox-backdrop" aria-label="Close"></a>
  <div class="lightbox-content">
    <a href="#!" class="lightbox-close" aria-label="Close">×</a>
    <img src="{{ '/assets/images/two-extremes.png' | relative_url }}" alt="Detailed side-by-side infographic contrasting black-box delegation with substantive control and radical transparency in AI-assisted research.">
    <p class="lightbox-caption">Two extremes of AI-assisted research — from black-box delegation to substantive control with radical transparency. Designed through a ChatGPT session (GPT-5.4 Thinking) and rendered with OpenAI <code>gpt-image-2</code> on 2026-04-23.</p>
  </div>
</div>

<div class="section-banner">
  <span class="num">I</span>
  <span class="label">Best Practices</span>
  <span class="sub">how to set up and run AI agents in research</span>
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

<p class="fig-caption">Setting up AI agents in the research process.</p>

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

<p class="fig-caption">A procedural approach to skill-building.</p>

## Context engineering in practice

Every agent run consumes a finite **context window**. Once it fills, the model starts forgetting earlier instructions, dropping constraints, and drifting between the unrelated tasks loaded into the same session. The discipline is to treat each model instance as **cheap and replaceable**: persistent knowledge lives in the project folder, not in the chat. A new session starts from a clean slate, pulls only what the task at hand requires, and runs a tight **plan → instruct → verify → correct** loop on artifacts the next instance can re-read.

That same project folder is what makes radical transparency possible. It doubles as a **sandbox repository** — a single directory carrying everything the agent needs (background concepts, literature, data, scripts, feedback) *and* a record of how each piece got there. Every asset is flagged for provenance (`human` / `agent` / `mixed`) and verification (`not-verified` / `partially-verified` / `human-verified`); every non-trivial agent session is logged. The replication package now documents the AI's role — not just the final data and code.

<figure class="hero-figure">
  <img src="{{ '/assets/images/context-management.png' | relative_url }}" alt="Stylized side-by-side infographic contrasting poor and strong context management in AI-assisted research.">
  <figcaption>Poor vs. strong context management — from a single saturated instance to a structured repository with a disciplined execution workflow.</figcaption>
  <p class="fig-cta"><a class="btn-fig" href="#fig-context-management-detail">View detailed infographic</a></p>
</figure>

<div id="fig-context-management-detail" class="lightbox" aria-hidden="true">
  <a href="#!" class="lightbox-backdrop" aria-label="Close"></a>
  <div class="lightbox-content">
    <a href="#!" class="lightbox-close" aria-label="Close">×</a>
    <img src="{{ '/assets/images/context-management-detail.png' | relative_url }}" alt="Detailed side-by-side infographic contrasting poor context management (single mixed instance, unstructured directory, looped disorganized workflow, context-window saturation) with strong context management (automatic intake into a structured repository and a plan-instruct-verify-correct execution workflow).">
    <p class="lightbox-caption">Poor vs. strong context management — full detail. Designed through a ChatGPT session (GPT-5.4 Thinking) and rendered with OpenAI <code>gpt-image-2</code> on 2026-04-24.</p>
  </div>
</div>

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

<p class="fig-caption">A sample project context setup.</p>

<div class="section-banner">
  <span class="num">II</span>
  <span class="label">Governance</span>
  <span class="sub">substantive control and radical transparency</span>
</div>

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

Both governing principles need to bite at the operational level. **Substantive control** means drawing a hard line between procedural work that may be delegated and substantive judgment that must not — and operating accordingly. **Radical transparency** means treating the project folder as the audit trail and releasing it as part of the replication package.

## How to decide when to use AI?

Before delegating any task, ask one question: is the work **procedural** or **substantive**? Procedural tasks are rote — the same steps repeated across projects, by many people, with a checkable target. Substantive tasks rely on knowledge that is idiosyncratic to your project: your question, your data, your priors, your interpretation. Agents excel at the former because they have seen the pattern many times. They fail at the latter because, with no idiosyncratic knowledge to retrieve, they fill the gap with plausible-sounding fabrication.

<div class="decide-grid">
  <div class="decide-col use">
    <h3>Procedural — delegate</h3>
    <p class="why"><strong>Why it works.</strong> Rote tasks repeat across projects; the model has seen the pattern many times. Output is checkable against a known target.</p>
    <ul>
      <li>code a specified estimation pipeline</li>
      <li>format tables and figures from results</li>
      <li>convert between data or document formats</li>
      <li>draft boilerplate sections (methods, data documentation)</li>
      <li>compile references on a keyword</li>
    </ul>
  </div>
  <div class="decide-col avoid">
    <h3>Substantive — keep with the researcher</h3>
    <p class="why"><strong>Why it fails.</strong> The required knowledge is idiosyncratic to this project — your question, your data, your priors. With nothing to retrieve, the model fills the gap with plausible-sounding fabrication.</p>
    <ul>
      <li>decide the research question</li>
      <li>choose which assumptions to make</li>
      <li>choose the identification strategy</li>
      <li>interpret coefficient estimates</li>
      <li>decide the central claim</li>
    </ul>
  </div>
</div>

<figure class="hero-figure">
  <img src="{{ '/assets/images/task-content-ai-error-control.png' | relative_url }}" alt="Diagram positioning research tasks along axes of substantive content and AI error vs. researcher control.">
  <figcaption>Where AI fits across research tasks — error and control as a function of task content.</figcaption>
</figure>

## How to report when AI was used?

Releasing data and code is no longer enough. When agents have drafted, decided, or executed parts of the work, a credible replication package must extend three layers further — to the **inputs, throughputs, and outputs of the AI-assisted process** itself:

- **Inputs** — the prompts, plans, and context materials given to the agent.
- **Throughputs** — the agent's reasoning, intermediate outputs, and sign-off gates.
- **Outputs** — final artifacts tagged with model and version metadata.

The paper proposes a feasible, low-friction implementation: two CSV ledgers maintained inside the project folder. An **asset registry** flags every artifact's provenance (`human` / `agent` / `mixed`) and verification status; an **interaction log** summarizes every non-trivial agent session (date, input, output, model metadata). The project folder itself, with the ledgers inside it, becomes the audit trail.

The cost is real — authors log, register, and verify; reviewers read, cross-check, and judge. The consoling point is that the same tools that raise the bar also help meet it: interaction logs are written in-session rather than reconstructed afterward, and asset registries are updated by the same agents that produce the assets.

## What's in the replication package

This site's companion repository <em>is</em> the project folder used to write the paper — released as a working replication package so readers can inspect every artifact, its provenance, and the full interaction history.

<div class="assets">
  <div class="asset">
    <h4><code>appendix/</code></h4>
    <p>Online appendix. Every asset cited in the main text, including the dogfooded skills: <code>startup-checklist</code>, <code>self-interview-example</code>, <code>project-setup</code>, <code>project-setup-existing</code>, <code>skill-writing</code>, <code>lit-review-protocol</code>, <code>skills-library-setup</code>, <code>skills-library-connection</code>.</p>
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

## Companion: AI OS scaffolding

The disciplined workflow this paper advocates is not specific to this project. It generalizes — across papers, teaching, advising, business — into a personal **AI Operating System** layered on top of a coding-grade harness like Claude Code. The public-tier components of Simone's setup are released as a starter library: protocol skills, five session-level personas (`chief-of-staff`, `researcher`, `writer`, `engineer`, `teacher`), and a `librarian` subagent for skill resolution.

It is methodology and governance scaffolding to fork and customize, not a turnkey product. A setup guide for **Claude Code (terminal)** ships now; **Claude desktop** and **Codex** entry points are forthcoming.

<p class="cta">
  <a class="btn btn-primary" href="https://github.com/simonepaciphd/ai-os-public" target="_blank" rel="noopener">🧰 AI OS starter library on GitHub</a>
</p>

## Citation

> Paci, Simone (2026). *With Great Powers: A Practical Guide to Agentic AI for Social Science Research.* Working paper. Replication package: [github.com/simonepaciphd/with-great-powers](https://github.com/simonepaciphd/with-great-powers)

## Contact

Simone Paci · Stanford University · [spaci@stanford.edu](mailto:spaci@stanford.edu)
