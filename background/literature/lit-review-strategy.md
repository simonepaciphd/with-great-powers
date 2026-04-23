# Lit-Review Strategy — Transparent Control

**Status:** 8 strands approved (2026-04-21). Anchors and qualitative constraints are agent proposals awaiting final sign-off. Research questions drafted per strand in `ai-inputs/lit-review-prompts/` (Phase 2).

Protocol: `C:\Users\spaci\Dropbox\Skills\lit-review-protocol.md`.

**No source quotas.** The search agent's stopping rule is *diminishing returns on both number and type of sources* — see `Skills/lit-review-prompt-template.md`. Strands are named and scoped; they are not ranked by importance or quota.

---

## Paper frame

- **Working title:** Transparent Control: A Practical Guide to Agentic AI for Social Science Research
- **Thesis:** Effective agentic-AI adoption in social-science research rests on two principles — researcher **control** (humans retain key decisions) and **radical transparency** (new reporting standards for human-agent collaboration).
- **Named interlocutors (proposed):** Pepinsky (engage and extend); Spirling (build on); Gordon, Samii, Su (build on and extend from data to process integrity); Stanford HAI 2026 (factual anchor); Munger (corroborate uptake claims). *Researcher to confirm / edit.*

## Eight strands

### Landscape

**L1. landscape-adoption-and-heterogeneity**
Stats and studies on uptake among researchers, heterogeneity by field / career stage / institutional resources. Feeds both §1.1 uptake framing and the §4.1 discipline-level-risk argument about productivity differentials correlated with resource access.
- Outline sections: §1.1, §4.1 (discipline-level risk)
- Anchors: `hai2026index`, Wiley 2025 researcher survey (84% figure), Munger submission-volume prediction.
- Qualitative constraints: include at least one source with a disciplinary breakdown and one on institutional / resource-access heterogeneity.

**L2. llms-as-research-methods**
LLMs used *as* research methods: text-as-data, classification and measurement, silicon samples. Not about workflows; about the epistemic object.
- Outline sections: §1.1 (frontier applications), §3.5
- Anchors: Argyle et al. silicon samples (to confirm); Grossmann et al. *Science* piece on AI transforming social science research.
- Qualitative constraints: include at least one critical / failure-mode paper.

**L3. llm-agents-as-research-infrastructure**
Multi-agent simulations and LLM-driven "societies" as infrastructure for studying social phenomena.
- Outline sections: §1.1 (frontier applications), §2.1 (agentic framing), §3.5
- Anchors: AgentSociety (arXiv:2502.08691); "Emergent social conventions…" (*Science Advances*, adu9368); multi-agent paradigm paper (arXiv:2506.01839).
- Qualitative constraints: include at least one validity / external-validity critique.

### Argument support

**A1. ai-in-the-research-process**
How practicing social scientists are using (and debating) agentic AI in the research workflow. The meta-conversation this paper joins.
- Outline sections: §1.1, §1.2, §3.5
- Anchors: `pepinsky2026agentic`, Brookings "train has left the station," Munger.
- Qualitative constraints: include at least one skeptical voice and at least one source from outside political science.

**A2. trust-in-ai-research** *(merged strand)*
Reliability, transparency, replicability, and research-integrity infrastructure. Covers: open-vs-closed model debate (Spirling); p-hacking / multiverse / specification search amplified by agents; infrastructure for integrity (Data-NoMAD, BITSS, pre-reg); model drift and reproducibility over time.
- Outline sections: §3.1, §3.3, §4.1 (reliability bullet), §4.2
- Anchors: `spirling2023nature` + Barrie/Palmer/Spirling + Spirling 2025/2026 talks; `gordon2025datanomad`; Simmons/Nelson/Simonsohn (2011); Gelman/Loken garden of forking paths; Steegen et al. multiverse.
- Qualitative constraints: balance across sub-topics (replicability, reliability risks, integrity infrastructure). Include at least one steelman of proprietary-LLM use.

**A3. control-and-research-decision-ownership**
Who decides what in human-agent research collaboration. Human-in-the-loop design, autonomy gradients, Pepinsky's "rules vs. interpretation" line, decision-audit norms.
- Outline sections: §1.3 (governing principle), §3.5, §4.1
- Anchors: `pepinsky2026agentic` (cross-tagged with A1); HCI / human-in-the-loop literature; STS work on automation and epistemic authority.
- Qualitative constraints: include at least one disagreement with the "keep humans in charge" frame, and at least one empirical / measurement study.

### Secondary scope

**B1. cognitive-effects-on-researchers**
Evidence on cognitive offloading, skill atrophy, expertise erosion from AI assistance. Anchors both "retain control" and "continuous skill-building."
- Outline sections: §4.1 (human learning), §4.3 (skill-building)
- Anchors: *(need researcher input)* — candidates include Bastani-style measurement studies and education-research on cognitive offloading.
- Qualitative constraints: include at least one quantitative measurement study (not commentary-only).

**B2. ethics-environment-privacy-of-llms**
Brief coverage for responsible acknowledgment in §4.1.
- Outline sections: §4.1 (ethical risks)
- Anchors: `hai2026index` (carries environment and privacy data).
- Qualitative constraints: keep scope light — this is acknowledgment, not deep engagement.

## Outstanding items for researcher sign-off before running

1. **B1 anchors** — do you have specific cognitive-effects papers in mind? If not, the prompt for B1 will open-endedly hunt, which is lower-confidence until reviewed.
2. **Munger source** — still blog / interview / paper? Primary cite needed.
3. **Wiley 2025 primary report** — location?
4. **Any strand to add or drop?** We explicitly decided not to add "institutional / departmental AI-readiness" as its own strand; confirm.
5. **Research questions per strand** — each strand's prompt file in `ai-inputs/lit-review-prompts/` has draft RQs in brackets awaiting your edits.

## Next steps

Once the above items are resolved:
- Confirm the deep-research tool(s) you'll use.
- Graduate each strand's file from `stub` → `ready-to-run`.
- Run. Drop raw outputs into the "Raw output" section of each strand file.
- I ingest through Phases 3–4.
