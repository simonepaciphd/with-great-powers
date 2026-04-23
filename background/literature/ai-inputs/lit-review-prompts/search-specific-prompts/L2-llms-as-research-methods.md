# L2 — llms-as-research-methods

**Strand:** L2 — llms-as-research-methods
**Status:** ready-to-run *(RQs drafted by agent; awaiting researcher sign-off)*
**Stopping rule:** diminishing returns on number and type (see prompt template).

**To execute:** Use the pre-merged file at `../finalized-prompts/L2-llms-as-research-methods.md` (template + context below). Paste it into your deep-research tool. Paste output into "Raw output." Regenerate the finalized file if the context block below changes.

---

## Prompt context

### Paper context
- **Title:** With Great Powers: A Practical Guide to Agentic AI for Social Science Research
- **Thesis:** Effective agentic-AI adoption in social-science research rests on two principles — researcher control and radical transparency.

### Strand
- **Name:** llms-as-research-methods *(LLMs used as research methods — text-as-data, silicon samples, classification and measurement. Not about agentic workflows.)*

### Research questions *(DRAFT — researcher to confirm / edit)*
1. What are the most methodologically influential applications of LLMs as measurement, classification, or coding tools in social-science research (2023–2026)? Which tasks do they perform reliably, and where have validation failures or systematic biases been documented?
2. What is the current state of the silicon-samples / LLM-as-respondent literature (original proposals, replication attempts, validity critiques)? Is consensus forming, fracturing, or fading?
3. What published methodological guidelines or reporting standards have emerged for LLM-based measurement or silicon-sample work (analogous to CONSORT or STROBE in other fields)?
4. What comparative evidence exists — when LLMs have been benchmarked against human coders, traditional supervised methods, or domain experts, what systematic conclusions about accuracy, bias, cost, and replicability have emerged?

### Anchor sources (do not re-discover — find adjacent work)
- Argyle et al. silicon samples *(confirm citation)*
- Grossmann et al., "AI and the transformation of social science research," *Science* *(confirm citation + year)*
- [Top text-as-data-with-LLMs papers — TBD]

### Scope overrides
- Time window: 2022–2026, emphasis 2024–2026.
- Publication types: peer-reviewed journals + top arXiv cs.CL / stat.ME.

### Exclusions
- Pure NLP benchmark papers without social-science application.
- Engineering-only papers on model architectures.

### Additional constraints
- Include at least one critical / failure-mode paper (e.g., bias in silicon samples, validity limits on LLM classification).

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
- [ ] Rows added to `classification.csv`
- [ ] `asset-registry.csv` updated
- [ ] `interaction-log.csv` updated
