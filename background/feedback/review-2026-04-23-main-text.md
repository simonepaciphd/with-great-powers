# Review of main.tex (main text only, appendix skipped)
**Date:** 2026-04-23
**Scope:** Abstract through §4 Conclusions in `C:\Users\spaci\Dropbox\Apps\Overleaf\AI in the Research Process\main.tex`.
**Lit inventory used:** `background/literature/references.bib` (mirrored into Overleaf `references.bib`, ~110 entries), the eight strand synthesis files under `background/literature/ai-inputs/`, and `classification.csv`.

Three dimensions:
1. **Content** — passages that feel underdeveloped relative to the paper's claims.
2. **Syntax/structure** — outright typos and sentences that read unclearly.
3. **Literature** — anchor sources already in `references.bib` that could carry specific claims.

Throughout, citations are noted with their exact bibtex key and in most cases a one-clause reason. Line numbers refer to the current Overleaf `main.tex`.

---

## Summary

- **Currently cited in main text:** `wiley2025adoption`, `hai2026aiindex`, `pepinsky2026agentic`, `hall2026`, `spirling2023opensource`, `spirling2026talks`, `gordon2025datanomad`, `mohammadi2026reshaping`, `chugunova2026germany`. Nine distinct entries.
- **Lit-review bib:** ~110 verified entries across 8 strands. The main text uses <10% of what's available.
- **Highest-leverage citation gaps:** §3.4 (prompt engineering) and the first half of §4 (risks/deskilling), both currently uncited, both with direct lit-review strand support.
- **Most urgent syntax fixes:** §3.1 line 97 (broken sentence — "IDE (i."), §3.3 line 141 (sentence fusion), §4 line 240 ("neet" for "meet"), §3.4 line 191 ("stirs" for "steers").

---

## §0 Abstract (line 27)

**Content.** The abstract front-loads the two principles but gives only one sentence to the workflow. Given the paper's main contribution is the workflow + infrastructure (Section 3), the abstract could devote one more sentence to what the replication package actually *contains* (asset registry, interaction log, skills library) rather than leaving "inputs, throughputs, and outputs" abstract.

**Syntax.** Fine.

**Citations.** Abstract does not take citations. No action.

---

## §1 Introduction (lines 31-38)

### §1 ¶1 — Motivation (line 34)

**Content.**
- The move from "84% of researchers adopt AI" to "26-28% YoY growth in AI-tagged publications in natural/physical/life sciences" is a slight bait-and-switch: the 26-28% is not about social science. Consider either (a) qualifying the sentence ("in adjacent sciences, AI-tagged publications..."), or (b) adding a social-science-specific depth-of-use point (see citations below) that is the actual story — headline adoption is high, but depth is shallow in social science, which sharpens the motivation.
- "The frontier is wider still" is a good pivot, but the two examples (`pepinsky2026agentic`, `hall2026`) both land on the same point (end-to-end agentic pipelines). Consider varying: Pepinsky for rule-following empirics and `abdurahman2025primer` or `davidson2025integrating` for the broader methods picture.

**Syntax.**
- "long assumed by the research community" is wordy; "long-assumed" or just "the research community has long assumed" reads cleaner.

**Citation opportunities.**
| Claim in text | Suggested cite(s) | Why |
|---|---|---|
| "84% adoption" (already has `wiley2025adoption`) | Also `oup2024researchersai` (76% in a 2,345-respondent global survey) | Cross-validates the headline; OUP gives discipline breakdowns |
| Depth-gap (new sentence to consider) | `mohammadi2026reshaping`, `alvero2026state`, `andersen2025genai` | Shows modal use is translation/editing, not agentic workflows — the paper's gap |
| "AI-tagged publications... 26-28% YoY" (has `hai2026aiindex`) | Also `arroyomachado2025academicscientists` | Parallel evidence from academic-scientists scan |
| "agentic pipelines now run routine empirical work end to end" (has `pepinsky2026agentic`) | Also `shah2026automating`, `hu2025reprobench` | Concrete agentic-reproducibility audits; grounds the "end-to-end" claim in measured capability |
| "ordinary anchors of authorship and replicability no longer sit where long assumed" | `spectorbagdady2025integrity`, `munger2026peer`, `munger2026scenarios` | Spector-Bagdady frames GenAI-in-research as a prospective integrity/governance problem; Munger scenarios are the governance complement |

### §1 ¶2 — Positioning (line 36)

**Content.** This is the thinnest paragraph in the intro. It claims a contrast with "a growing body of work that frames AI's implications for social science in programmatic or speculative terms" but **names no one**. The reader has no way to triangulate what the paper is positioning against. Two easy fixes:
- Add one or two representative citations for the programmatic/speculative side (e.g., `grossmann2023transformation`, `korinek2023generative`, `lu2024scientist`).
- Add one sentence to contrast with the methods-paper literature that *is* already concrete and close in spirit, acknowledging it (`abdurahman2025primer`, `davidson2025integrating`, `stuhler2025promptbooks`) so the paper's distinctive contribution — workflow-level, agent-era, governance-integrated — is crisper.

**Syntax.** Fine.

**Citation opportunities.** See above.

### §1 ¶3 — Core principles (line 38)

**Content.** Principles are stated cleanly, but the reader has to wait until §4 to see any lit anchor. One compact sentence each, tying the two principles to their lit, would pay off:
- **Control.** Pepinsky's rule-vs-interpretation line is the nearest interlocutor and is already cited in §1 ¶1; you can re-invoke it here ("extending the rule-following boundary Pepinsky 2026 proposes"). Normative complement: `davidovic2023purpose`, `siebert2023meaningful`.
- **Transparency.** The locus of the expanded replication argument is `spirling2023opensource` + `barrie2025replication`; the reporting-standards side is `holst2025prismatraice`, `aer2026aipolicy`, `apsr2026aitools`; the integrity-infrastructure side is `gordon2025datanomad` (already cited in §3.3) and `spectorbagdady2025integrity`.

**Syntax.** Fine.

---

## §2 The AI Vocabulary (lines 41-65)

### §2.1 Fundamentals (line 46)

**Content.**
- The hallucination / false-negative typology is a strong original contribution in the paper. It currently stands alone. Anchoring the false-negative point in at least one existing finding would strengthen it — `ashwin2025bias` documents systematic-bias failure modes; `halterman2026codebook` shows codebook delegation failures; `baumann2025hacking` shows prompt-induced directional bias. Any one of these converts the paragraph from assertion to claim-with-support.

**Syntax.**
- Line 49: "**researcher** still need to ``do the work''" → "**researchers** still need". Agreement.
- Line 49: `one needs ``only'' check the work` — the scare quotes on *only* are awkward; consider `one ``only'' needs to check the work` or drop the quotes: `one only needs to check the work`.
- Line 49 footnote: "usually not persistent and user-accessible" reads a little truncated; either "usually neither persistent nor user-accessible" or a full sentence.

**Citation opportunities.**
| Claim | Suggested cite(s) |
|---|---|
| Hallucinations (false positives) | `pepinsky2026agentic` (citation-fabrication note), `abdurahman2025primer` (validation discipline) |
| False-negative errors (systematic silent omissions) | `ashwin2025bias`, `halterman2026codebook`, `baumann2025hacking` |

### §2.2 Key Components (line 57)

**Content.**
- The three-stage prompt → context → harness arc is a nice narrative, but it is presented as stylized fact. Worth anchoring at least the prompt-engineering step (where the literature is mature): `stuhler2025promptbooks`, `ornstein2025stochastic` treat prompts as measurement instruments.
- "two objects do most of the customization work inside the harness" — the skill/orchestration framing is novel; keep as is, but consider one sentence flagging that `stuhler2025promptbooks` is the closest published sibling concept (structured prompt libraries → skill libraries).

**Syntax.**
- Line 60: "a third frontier has opened **more recently** around the runtime itself" — "more recently" is redundant after "has opened". Cut.
- Line 64: "agents are no different. They need as precise a scaffolding..." — "as precise a scaffolding as the researcher can provide" reads a little stiff; "scaffolding as precise as the researcher can provide" flows better.

---

## §3 How to Deploy Agentic AI Effectively (lines 67-228)

### §3 opener (line 71)
Fine. No changes.

### §3.1 Choice of Toolset (line 94)

**Content.**
- This is the closest the paper comes to a "choose your tool" chapter; currently it only names four harnesses and flags the frontier-vs-open-weights trade-off. A reader wanting "which one and why" gets little. Consider a second paragraph (or footnote) that at least acknowledges the pricing/capability/ecosystem heterogeneity more concretely — `hai2026aiindex` already supports the capability-leader shifts claim.
- The open-weights argument stands almost entirely on Spirling. `barrie2025replication` is the most natural companion (political-science-specific, directly about LM replication) and is already in the bib.

**Syntax.** 🚨
- **Line 97:** "The first researcher choice concerns which GenAI model and IDE (i. The current landscape..." — broken sentence. The `(i.` appears to be a drafting artifact (enumeration fragment). Fix to "... which GenAI model and which IDE to adopt. The current landscape...".
- Line 97: "IDE plug-ins for VS~Code and terminal-based environments" — VS Code *is* an IDE; "IDE plug-ins for VS~Code and terminal environments" would be cleaner (drop "-based").

**Citation opportunities.**
| Claim | Suggested cite(s) |
|---|---|
| "at least three frontier providers in active competition" | `hai2026aiindex` (already cited; this is the anchor for the shifting-frontier claim) |
| "the capability frontier has shifted several times in the last year alone" | `hai2026aiindex` (same); optionally `thomas2026jagged` (jagged performance across models/tasks) |
| Open-weights replicability argument | `barrie2025replication`, `palmer2024explicit` (already have `spirling2023opensource` + `spirling2026talks`) |
| Drift/model-versioning risk on closed models | `chen2024behavior`, `barrie2025promptstability` |

### §3.2 Harness Engineering (line 101)

**Content.**
- Security paragraph (line 104) is good framing but ends with an ask-the-literature sentence ("A larger discussion of security, beyond the scope..."). That's fine, but the `hai2026aiindex` citation there is doing a lot of work for "alignment + jailbreaking". Consider naming the specific HAI Index sub-result (the Transparency Index drop, agent-misuse benchmarks).
- Skill library subsection (line 106) is entirely prescriptive. Adding `stuhler2025promptbooks` ("promptbooks" as a structured, reusable prompt artifact) gives the closest lit anchor and strengthens the claim that this is not idiosyncratic advice.
- The "orchestration patterns" paragraph (line 132) is abstract; one concrete example ("e.g., a literature-review protocol that dispatches a search subagent and returns BibTeX under verification rules — see appendix") would land better. The infrastructure is there, it's just not cross-linked.

**Syntax.**
- Line 104: "**One the other hand**, the model could be quarantined to **a sandboxed** and given minimal permissions." → "**On the other hand**, the model could be quarantined to **a sandbox** and given minimal permissions."
- Line 104: "delete years worth" → "years' worth" or "years of work".
- Line 106: "each project should offer the opportunity to either create new skills or review old skills" — "or review/update existing skills" or just "review old ones" for less repetition.
- Line 108: "self-interviews" → "a self-interview" (singular, matches preceding article).
- Line 108: "practical ``tacit knowledge''" — either drop the scare quotes on *tacit knowledge* (it's a standard term) or italicize; scare-quoting is unneeded.

**Citation opportunities.**
| Claim | Suggested cite(s) |
|---|---|
| "Agentic AI must be granted access... substantial risks" | `hai2026aiindex` (already); `korinek2023generative` for the productivity/risk trade-off |
| Skill library as organized, reusable procedure | `stuhler2025promptbooks` (directly analogous — promptbooks as library) |
| Skill-crafting combines external sources + researcher's tacit knowledge | `abdurahman2025primer` (validation discipline), `davidson2025integrating` (methods-map framing) |

### §3.3 Context Engineering (line 134)

**Content.**
- Strong section overall. The cryptographic-authentication footnote (`gordon2025datanomad`) is well-placed.
- Paragraph 4 (line 143): "Such complex context scaffold may seem like a burdensome request of researchers." This is a good anticipated-objection move; the response relies on the project-setup skill. Consider adding one sentence on the broader reporting-standards context so the scaffold doesn't read as purely idiosyncratic: journals are moving this direction (`aer2026aipolicy`, `apsr2026aitools`, `holst2025prismatraice`).
- "establishing trust in an AI-supported research process" (line 145) could cite the disclosure literature: `aer2026aipolicy`, `apsr2026aitools`, `holst2025prismatraice`, `spectorbagdady2025integrity`.

**Syntax.** 🚨
- **Line 141:** "Part of the project orchestration, implementable through the README file, should **instruct agents to log all non-trivial session should be summarized** in an interaction log that records date, researcher input, agent output, and model metadata." — two sentences fused. Fix to: "...should instruct agents to log every non-trivial session in an interaction log that records date, researcher input, agent output, and model metadata."
- Line 137: "as if they were sharing it with an RA" — match §2.2's "research assistant" for consistency (or define RA on first use).
- Line 139: "Finally, clear instructions on routine cleanups through a system of archive subfolders..." — sentence fragment (no main verb). Either "Finally, clear instructions **should cover** routine cleanups..." or integrate with the sentence before.
- Line 143: "render**s** its directory tree" — subject agreement with "Figure": fine, but "renders its directory tree alongside the workflows layered on top" reads awkwardly. "shows a sample directory tree with its supporting workflows" is crisper.

**Citation opportunities.**
| Claim | Suggested cite(s) |
|---|---|
| "asset registry... verification status" | `abdurahman2025primer` (validation discipline), `holst2025prismatraice` (reporting checklist) |
| "interaction log that records... model metadata" | `aer2026aipolicy`, `apsr2026aitools`, `holst2025prismatraice`, `barrie2025replication` |
| "cryptographic authentication of research artifacts" (already has `gordon2025datanomad`) | keep |
| "establishing trust in an AI-supported research process" | `spectorbagdady2025integrity` (governance framing), `spirling2023opensource`, `barrie2025replication` |

### §3.4 Prompt Engineering (line 188)

**Content.**
- Entirely uncited. This is the single biggest gap in the paper. The prompt-engineering / prompt-sensitivity literature is rich and directly supports every claim in the section.
- ¶1 (line 191): "the burden on prompt engineering is... inversely proportional to quality of the harness and task-related skills" — this is a substantive claim and warrants at least one anchor. `stuhler2025promptbooks` directly supports the idea that a well-stocked prompt/skill library reduces per-prompt burden.
- ¶2 (line 193): "the model's decisions will be shaped by priors the researcher cannot easily audit" — `barrie2025promptstability`, `baumann2025hacking`, `chen2024behavior`, `carlson2026annotation` all show exactly this.
- ¶2: "A prompt that does not specify how a task should be done is a prompt that delegates method to the model" — classical forking-paths analogues: `simmons2011falsepositive`, `gelman2013forking`, `steegen2016multiverse`. Pepinsky's p-hacking concern (already cited) is the contemporary version.
- ¶3 (line 195): The self-interview paragraph now cross-refs Appendix B. Good. Consider one sentence tying back to skill-building (which you do call out via "akin to the skill-building process") with `stuhler2025promptbooks` as the anchor.

**Syntax.**
- **Line 191:** "stirs the ship" → "**steers** the ship". (Typo.)
- Line 191: "Across specific tasks, the burden on prompt engineering is, at least in part, inversely proportional to quality of the harness and task-related skills." — "to **the** quality of the harness".
- Line 193: "A good plan is goal-oriented and articulated iteratively before the agent begins executing." → "articulated iteratively **with the agent** before the agent begins executing" (otherwise the iteration partner is unspecified).
- Line 193: "a sequence of **short** more controllable and accountable ones." → "a sequence of **shorter,** more controllable and accountable ones."

**Citation opportunities.**
| Claim | Suggested cite(s) |
|---|---|
| "burden inversely proportional to harness + skills quality" | `stuhler2025promptbooks` |
| "priors the researcher cannot easily audit" | `barrie2025promptstability`, `chen2024behavior`, `carlson2026annotation`, `baumann2025hacking` |
| "a prompt that does not specify method delegates method" | `pepinsky2026agentic` (already), + classical `simmons2011falsepositive`, `gelman2013forking`, `steegen2016multiverse` |
| "one instance for one task" | `tankelevitch2024metacognitive` (metacognition under LLM use); can also cite context-drift / effectiveness literature if the paper wants empirical rather than prescriptive grounding |

### §3.5 Agent Management (line 199)

**Content.**
- Paragraph 1 (line 202) argues for weighing "procedural vs. substantive" as the deployment criterion. This is the strongest Pepinsky echo in the paper and should re-cite `pepinsky2026agentic` explicitly. You can extend with `halterman2026codebook` (delegation failures on substantive coding) and `ashwin2025bias` (systematic-bias failure modes).
- Figure 4 (line 204–226) lists candidate applications by stage. Each stage has a lit anchor if you want the figure caption to reference one:
  - **Question stage** ("scope literatures..."): `digiuseppe2026scaling`, `davidson2025integrating`
  - **Theory** ("implications of assumptions..."): less developed lit; `horton2023homosilicus` for theory-adjacent simulation, `kozlowski2025simulating` as cautious counterpoint
  - **Empirics** ("implement pipelines..."): `gilardi2023`, `tornberg2024annotation`, `choi2026expertcoding`, `manning2024automated`, `shah2026automating`
  - **Writing** ("draft, edit, compress..."): `korinek2023generative`, `mohammadi2026reshaping`
- Paragraph on monitoring/verification (line 228) lists three review layers with zero citations. The oversight/contestability literature strand (A3) was built for exactly this:
  - Dual chain-of-thought review → `amershi2019guidelines` (HCI design guidelines for human-AI interaction), `tankelevitch2024metacognitive`
  - Secondary validation checks → `abdurahman2025primer`, `halterman2026codebook`, `ashwin2025bias`
  - Review-agent team → `schmidgall2025agentlab`, `lu2024scientist` (as the automation end of the spectrum the paper is *not* advocating), `siebert2023meaningful` / `alfrink2023contestable` (contestability as lifecycle design)

**Syntax.**
- Line 202: "The first, obvious question **pertains** when to deploy agents." → "pertains **to** when".
- Line 202: "the researcher should weight the balance between procedural and substantive nature of the task" → "should **weigh** the balance..." (typo: "weight" vs "weigh").
- Line 202: "understanding these aspects as **non mutually exclusive**" → "non–mutually-exclusive" or "not mutually exclusive".
- Line 202: "say making the tikz package produce **table** \ref{fig:skill-build}" — the referenced object is Figure 2 (a figure, not a table), and the self-referential example works only if the right object is named. Either: "say making the TikZ package produce **Figure \ref{fig:skill-build}**", or rework the example entirely (there's also a small style question of whether the reader should be asked to hold the skill-building figure in mind at this moment).
- Line 228: "three layers **to** this mandate" — "of this mandate" reads more naturally.
- Line 228: "the agent's reasoning **may flag** mistakes and drift" — OK but passive; "parsing the reasoning **can surface** mistakes and drift" is crisper.

**Citation opportunities.** (Combined from above)

### §3 overall

- §3.1 has 3 citations; §3.2, §3.4, §3.5 have none. §3.3 has one. The paper is presenting a workflow as a synthesis of practice, but the synthesis currently reads as argued-from-nowhere in §3.2-3.5. Even one well-chosen citation per subsection (ideally two-three) would change the posture from "here's my view" to "here's my view, which coincides with the current methods literature in the following specific ways."

---

## §4 Conclusions (lines 231-244)

Structurally, §4 has no subsections in the current version (the roadmap had §4.1-§4.4). That may be deliberate — the prose does flow as an essay — but it makes cross-referencing harder. Consider either (a) restoring the four subsections or (b) at least tagging the four arguments with italicized phrase-openers so readers can navigate: "*On transparency*...", "*On further risks*...", "*On the shelf life of this advice*...".

### §4 ¶1 — Open questions (line 234)

**Content.** Good ambition-setting. No change needed.

**Syntax.**
- Line 234: "what **is the value of** a human researcher **is**" — doubled "is". Delete the second.
- Line 234: "a messy **evolving** of disciplinary practice" → "a messy **evolution** of disciplinary practice".

### §4 ¶2 — Abstract defense (line 236)

**Syntax.** Fine.

### §4 ¶3 — Transparency (line 238)

**Content.** Strong paragraph; carries the paper's most distinctive prescription. It should cite something.

**Citations.**
- "expanded notion of a replication package" — `spirling2023opensource`, `barrie2025replication`, `holst2025prismatraice`, `spectorbagdady2025integrity`
- "what the researcher prompted, which model and version answered..." — this is almost exactly the disclosure literature: `aer2026aipolicy`, `apsr2026aitools`, `holst2025prismatraice`, `palmer2024explicit`

### §4 ¶4 — Burden response (line 240)

**Syntax.** 🚨
- **Line 240:** "the same tools that raise the bar also help **neet** it" → "**meet** it". (Typo.)
- Line 240: "reviewers who must engage it" → "reviewers who must engage **with** it".
- Line 240: "the same logic could apply to standardizing and automating the systematic review of this process" — "systematic review" has a specific methodological meaning; here you mean reviewer-side audit. Consider "the systematic **review of AI-assisted papers**" or "the automated audit of this process" to avoid the term collision.

**Citations.** `munger2026peer` is directly about this (automating peer review). `holst2025prismatraice`, `aer2026aipolicy`, `apsr2026aitools` support the standardized-reporting half.

### §4 ¶5 — Further risks (line 242)

**Content.** 🚨 Biggest citation gap in the paper. The paragraph flags **four** distinct risks and cites lit on only one (productivity gaps). Strand B1 (cognitive effects) and strand B2 (environment/privacy) were built for this paragraph.
- **Deskilling ("slow erosion... skills"):** `lee2025critical`, `shen2026skill`, `bastani2025guardrails`, `gerlich2025offloading`, `fan2025laziness`, `shihab2025copilot`, `tankelevitch2024metacognitive`. (Pick two or three — don't flood.)
- **Speed/depth trade-off:** `lee2025critical`, `fan2025laziness`, `prather2024widening`. Also `tankelevitch2024metacognitive` for the metacognitive-weakening mechanism.
- **Uneven adoption → productivity gaps:** `mohammadi2026reshaping`, `chugunova2026germany` (already cited); add `bianchini2025drivers` for the democratizing-countercurrent claim, and consider `cruces2026education` (RCT evidence AI can narrow education-based productivity gaps — direct support for the countercurrent).
- **Environment / privacy / society:** `xiao2025netzero`, `iea2025energy`, `king2026privacy`, `carlini2023memorization`, `nasr2025extraction`.

**Syntax.**
- Line 242: "Agents can do almost every operational task involved in producing a paper, and that possibility threatens a slow erosion of the underlying researcher's skills." — "the **underlying** researcher's skills" reads oddly; "the researcher's own skills" or just "the researcher's skills" is cleaner.
- Line 242: "this paper offers no principled way to calibrate the trade-off between speed and depth" — this is an honest limit; consider framing it as a research agenda ("calibrating this trade-off remains an open question, and empirical grounds for doing so are still thin — see `lee2025critical`, `fan2025laziness`").

### §4 ¶6 — Shelf life and shared infra (line 244)

**Content.** The ask for community infrastructure is aspirational; no citations strictly required, but:
- "shared harnesses, maintained skills libraries, and review routines" — you can gesture at `spirling2023opensource` + `spirling2026talks` for the community-infrastructure ask, and `xin2026ailiteracy` for the AI-literacy-as-institutional-responsibility line.

**Syntax.**
- Line 244: "institutional responsibility **on both sides**" — ambiguous. Both sides of what? If you mean training + infrastructure, say so.
- Line 244: "**shared** harnesses, **maintained** skills libraries, and review routines that make credible reporting feasible at scale" — consistent series structure would help: "through shared harnesses, maintained skills libraries, and **standardized** review routines".

---

## Cross-cutting observations

### Literature density
The paper makes a distinctive, strong prescription — but a reader coming from the methods literature will notice the thin referencing. The lit-review bib was built to carry exactly this paper; roughly 20-30 additional, well-placed citations (distributed across §1 ¶2, §3.2-§3.5, §4 ¶3, §4 ¶5) would visibly raise the density without making prose feel overstuffed. Concentrate in §3.4 and §4 ¶5, which are the lightest.

### Consistency of voice
The paper's strongest voice is in §3 (workflow prescriptions) and §4 (principles). §2 is still in "primer" voice; §1 ¶2 is in "abstract positioning" voice. Decide whether §2 should occasionally editorialize (it currently only does so in the hallucination/false-negative passage) or stay didactic.

### §4 subsection structure
The current essayistic structure works, but loses the direct cross-reference the abstract invites ("two core governance principles... [see §4.2]"). Minimal fix: italic phrase-openers. Heavier fix: restore the four subsections.

### Figure 4 caption
Line 226: caption is "Research Stages and Candidate Agentic AI Applications" — currently a label with no explanatory body. Consider a one-sentence caption that names the principle (procedural vs. substantive) and the key asymmetry (agents shine on the former, falter on the latter), to save the reader from reconstructing it from the main text.

### Table 1 integration
Table 1 is introduced at line 44 and typeset via `\input{tables/table1-vocabulary}` on line 55, which means it is embedded in §2.1 before §2.2's "Key Components" concepts (skill, orchestration) have been defined. If Table 1 contains *skill* and *orchestration* rows (it should, per the roadmap), consider either moving the `\input` to after §2.2 or splitting the table.

### Self-citation loop
§3.3 says "I wrote this chapter following this system and provide the full replication package as a template example" (line 143). This is a powerful dogfooding claim and belongs in the abstract too — one sentence would do. It is currently under-advertised.

---

## Quick-fix checklist (typos and broken sentences)

- [ ] Line 49: "researcher" → "researchers"
- [ ] Line 60: delete "more recently"
- [ ] Line 97: fix "IDE (i." broken sentence
- [ ] Line 104: "One the other hand" → "On the other hand"; "a sandboxed" → "a sandbox"
- [ ] Line 139: supply main verb in "Finally, clear instructions on routine cleanups..." sentence
- [ ] Line 141: untangle the fused sentence ("instruct agents to log all non-trivial session should be summarized")
- [ ] Line 191: "stirs the ship" → "steers the ship"; "to quality" → "to the quality"
- [ ] Line 193: "short more controllable" → "shorter, more controllable"
- [ ] Line 202: "pertains when" → "pertains to when"; "weight the balance" → "weigh"; "non mutually exclusive" → "not mutually exclusive"; **table** → **figure** in "produce table \ref{fig:skill-build}"
- [ ] Line 234: "what is the value of a human researcher is" → delete second "is"; "messy evolving" → "messy evolution"
- [ ] Line 240: "neet" → "meet"; "engage it" → "engage with it"
- [ ] Line 244: clarify "on both sides"

---

## Appendix — Citations indexed by theme (all keys verified in `references.bib`)

**Adoption & heterogeneity (L1 strand):** wiley2025adoption, oup2024researchersai, mohammadi2026reshaping, chugunova2026germany, andersen2025genai, arroyomachado2025academicscientists, alvero2026state, bianchini2025drivers, dortagonzalez2024usage, galjak2025generational, hai2026aiindex.

**LLMs as research methods (L2 strand):** gilardi2023, ziems2024, tornberg2024annotation, tornberg2025outperform, heseltine2024substitute, mellon2024issue, ornstein2025stochastic, halterman2026codebook, stuhler2025promptbooks, debelak2025embeddings, abdurahman2025primer, abdurahman2024perils, bisbee2024synthetic, dominguezolmedo2024questioning, gao2025caution, weidmann2026democracy, baumann2025hacking, mclaren2026magic, horton2023homosilicus, argyle2023out, sun2024random.

**Agents as infrastructure (L3 strand):** piao2025agentsociety, park2023generative, vezhnevets2023concordia, ashery2025conventions, larooij2025validation, li2024econagent, hou2025vaccine, park2024people, tomasevic2025operational, neumann2026opinions, ji2026citation, haase2025paradigm, taillandier2025abss, donkers2025polarization, zhou2024fantasy, andric2026mismatch, hullman2026behavioral.

**AI in the research process (A1 strand):** abdurahman2025primer, davidson2025integrating, bail2024generative, ornstein2025stochastic, stuhler2025promptbooks, digiuseppe2026scaling, hu2025reprobench, shah2026automating, messing2026train, pepinsky2026agentic, munger2026peer, munger2026scenarios, alvero2026state, broska2025mixed, lyman2025balancing, benoit2026nlu.

**Trust & replicability (A2 strand):** spirling2023opensource, spirling2026talks, palmer2024explicit, barrie2025replication, barrie2025promptstability, chen2024behavior, carlson2026annotation, thomas2026jagged, lyman2025balancing, abdurahman2025primer, tornberg2024annotation, stuhler2025promptbooks, lin2025fallacies, gordon2025datanomad, holst2025prismatraice, aer2026aipolicy, apsr2026aitools, korinek2023generative, simmons2011falsepositive, gelman2013forking, steegen2016multiverse.

**Control & decision ownership (A3 strand):** pepinsky2026agentic, halterman2026codebook, ashwin2025bias, amershi2019guidelines, davidovic2023purpose, siebert2023meaningful, alfrink2023contestable, yurrita2023fairness, yurrita2025needs, gilardi2023, choi2026expertcoding, palmer2024explicit, bartsch2025epistemic, hauswald2025artificial, lu2024scientist, schmidgall2025agentlab, lyons2021contestability, bisbee2024synthetic.

**Cognitive effects (B1 strand):** lee2025critical, shen2026skill, fang2025criticalpaper, tankelevitch2024metacognitive, shihab2025copilot, gerlich2025offloading, prather2024widening, fan2025laziness, bastani2025guardrails, kazemitabaar2024engagement, tian2026aact, xin2026ailiteracy, gaube2021susceptibility, margulieux2024selfregulation.

**Ethics, environment, privacy (B2 strand):** hai2026aiindex, xiao2025netzero, iea2025energy, spectorbagdady2025integrity, king2026privacy, carlini2023memorization, nasr2025extraction, oecd2025pets, oecd2025sharing, jones2025qualitative, linardon2025eating, bick2024adoption, brynjolfsson2023work, humlum2025labor, cruces2026education, bai2025persuade, salvi2025gpt4.

---

*End of review. Treat this as a punch list: accept, reject, or defer each line item. Citations are suggestions based on lit already verified in the bib; none are required.*
