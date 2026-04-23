# A2 — trust-in-ai-research

**Strand:** A2 — trust-in-ai-research *(merged strand: reliability + transparency + replicability + integrity infrastructure)*
**Status:** ready-to-run *(RQs drafted by agent; awaiting researcher sign-off)*
**Stopping rule:** diminishing returns on number and type (see prompt template).

**To execute:** Use the pre-merged file at `../finalized-prompts/A2-trust-in-ai-research.md` (template + context below). Paste it into your deep-research tool. Paste output into "Raw output." Regenerate the finalized file if the context block below changes.

**Note:** this strand covers three sub-topics (replicability, reliability risks, integrity infrastructure). Consider splitting the run into two passes if the deep-research tool returns noisy or unfocused results.

---

## Prompt context

### Paper context
- **Title:** With Great Powers: A Practical Guide to Agentic AI for Social Science Research
- **Thesis:** Effective agentic-AI adoption in social-science research rests on two principles — researcher control and radical transparency.

### Strand
- **Name:** trust-in-ai-research
- **Sub-topics covered:** (a) replicability with proprietary vs. open-weight LLMs; (b) p-hacking / multiverse / specification-search risks amplified by agents; (c) infrastructure for integrity (data attestation, pre-registration, replication archives); (d) model drift and reproducibility over time.

### Research questions *(DRAFT — researcher to confirm / edit)*
1. What is the current empirical case for the claim that proprietary-LLM-based research is non-replicable? What specific mechanisms — version updates, silent drift, RLHF changes, prompt sensitivity, sampling randomness — have been documented in peer-reviewed or high-quality working-paper work?
2. What is the empirical case for or against open-weight alternatives on replicability, capability, and researcher uptake grounds? Who are the main advocates (beyond Spirling) and who articulates the steelman for staying with proprietary models?
3. How have classical methodological concerns — p-hacking, garden of forking paths, multiverse analysis, specification search — been re-theorized or re-demonstrated when LLMs or agents enter the analytic pipeline? Are there named failure modes specific to agentic research?
4. What research-integrity infrastructure has been proposed or deployed beyond Data-NoMAD — e.g., pre-registration adapted for AI-assisted work, cryptographic attestation of prompts and outputs, containerized reproducibility environments, versioned-prompt archives?
5. Are there empirical studies measuring reproducibility failure rates for LLM-assisted empirical work, across time (model updates), across researchers, or across prompt variations?
6. What normative or editorial proposals have emerged from journals, editors, funders, or professional associations (APSA, SPSA, ASA, AEA) for transparency and reporting standards specific to LLM-assisted research?

### Anchor sources (do not re-discover — find adjacent work)
**Replicability / open vs. closed:**
- Spirling, "Why open-source generative AI models…" *Nature* 2023 — https://www.nature.com/articles/d41586-023-01295-4
- Barrie, Palmer, Spirling, "Trust Me Bro" — https://arthurspirling.org/documents/BarriePalmerSpirling_TrustMeBro.pdf
- Spirling 2025/2026 talks at Stanford Political Science and Yale ISPS.

**Integrity infrastructure:**
- Gordon, Samii, Su, "Data-NoMAD" (arXiv:2501.14651) — https://arxiv.org/abs/2501.14651
- BITSS (Berkeley Initiative for Transparency in the Social Sciences) — https://www.bitss.org

**Classical reliability:**
- Simmons, Nelson, Simonsohn, "False-Positive Psychology" *(2011, Psych Sci)*
- Gelman & Loken, "The Garden of Forking Paths" *(2013/2014)*
- Steegen et al., "Increasing Transparency Through a Multiverse Analysis" *(2016, Perspect Psychol Sci)*

### Scope overrides
- Time window: classical methods pieces may be older (2011+); LLM-specific reliability should be 2023–2026.
- Disciplines: social science + methodology + computational social science.

### Exclusions
- Purely theoretical CS papers on model evaluation without social-science hook.
- Individual replication-failure case studies unless illustrative of a broader pattern.

### Additional constraints
- Balance across sub-topics — do not let any one sub-topic crowd out the others.
- Include at least one steelman of proprietary-LLM use (for §3.1 balance).

---

## Raw output (fill after run)

[paste agent output here]

---

## Ingestion checklist
- [ ] BibTeX entries validated
- [ ] Each URL/DOI verified
- [ ] PENDING reviewed with researcher
- [ ] Deduped against `references.bib`
- [ ] Entries appended to `references.bib`
- [ ] Rows added to `classification.csv` (note: most A2 sources will cross-tag with sections 3.1, 3.3, 4.1, 4.2)
- [ ] `asset-registry.csv` updated
- [ ] `interaction-log.csv` updated
