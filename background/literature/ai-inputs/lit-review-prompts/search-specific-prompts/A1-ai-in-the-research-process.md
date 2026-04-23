# A1 — ai-in-the-research-process

**Strand:** A1 — ai-in-the-research-process
**Status:** ready-to-run *(pending researcher approval of research questions)*
**Stopping rule:** diminishing returns on number and type (see prompt template).

**To execute:** Use the pre-merged file at `../finalized-prompts/A1-ai-in-the-research-process.md` — it combines the template + the "Prompt context" block below. Paste it into your deep-research tool of choice. Paste the agent's output into the "Raw output" section when received. If the context block below changes, regenerate the finalized file.

---

## Prompt context

### Paper context
- **Title:** Transparent Control: A Practical Guide to Agentic AI for Social Science Research
- **Thesis:** Effective agentic-AI adoption in social-science research rests on two principles — researcher **control** (humans retain key decisions) and **radical transparency** (new reporting standards for human-agent collaboration).

### Strand
- **Name:** ai-in-the-research-process

### Research questions
1. Which practicing social scientists (economics, political science, sociology, psychology) have published positions, primers, or critiques on agentic AI in research practice in 2024–2026?
2. What are the main lines of disagreement about what agents should and should not do in the research process?
3. What concrete workflow recommendations or design principles have been proposed?
4. Are there documented cases of agentic AI producing research outputs that made it into published work (good or bad)?

### Anchor sources (do not re-discover — find adjacent work)
- Pepinsky, "Agentic AI and Social Science Research Practice." Blog, 2026-01-23. https://tompepinsky.com/2026/01/23/agentic-ai-and-social-science-research-practice/
- Brookings, "The train has left the station: Agentic AI and the future of social science research." https://www.brookings.edu/articles/the-train-has-left-the-station-agentic-ai-and-the-future-of-social-science-research/
- Kevin Munger — predictions re: submission volume to top political-science journals.

### Scope overrides
- Time window: 2020–2026, emphasis 2024–2026.
- Disciplines: political science, economics, sociology, psychology.
- Publication types: peer-reviewed journals + top working papers + high-signal blog posts by recognized researchers (flag the blogs as `low` reliability per template).

### Exclusions
- Vendor whitepapers, consulting reports without method transparency.
- Pre-2023 pieces unless canonical.
- Marketing material.

### Additional constraints
- Include at least one skeptical voice.
- Include at least one source from outside political science.

---

## Raw output (fill after run)

[paste agent output here]

---

## Ingestion checklist
- [ ] BibTeX entries validated (required fields + reliability + access tags)
- [ ] Each URL/DOI verified to resolve
- [ ] PENDING entries reviewed with researcher
- [ ] Deduped against existing `references.bib`
- [ ] Entries appended to `references.bib`
- [ ] Rows added to `classification.csv`
- [ ] `asset-registry.csv` updated
- [ ] `interaction-log.csv` updated
