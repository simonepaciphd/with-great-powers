# llms-as-research-methods — Literature landscape

## Top 3 most relevant sources
1. halterman2025codebook — The best direct fit for this strand because it treats LLMs explicitly as measurement instruments and tests whether they follow real political-science codebooks.
2. bisbee2024synthetic — The clearest peer-reviewed critique of silicon-sample use in survey research and the best corrective to overly optimistic “LLM-as-respondent” claims.
3. abdurahman2025primer — The strongest current source on validity, replicability, and reporting expectations for LLM-based social-science research.

## Themes identified
- **LLMs often work well as bounded annotators, but performance is task-conditional**: Across text labeling, survey coding, and political-text annotation, LLMs often match or beat crowd workers and sometimes rival experts. But gains are strongest on shorter, cleaner, better-specified tasks; fine-tuned conventional models still win in many benchmark settings. Representative sources: gilardi2023chatgpt, ziems2024transform, heseltine2024substitute, tornberg2025outperform, mellon2024issue.
- **The literature is shifting from “can they annotate?” to “how should they be validated?”**: Newer work treats prompts, codebooks, and model choice as parts of the measurement instrument itself. This produces a more methodological literature centered on preregistration, validation against human judgment, prompt architecture, and transparent implementation reporting. Representative sources: ornstein2025stochastic, halterman2025codebook, stuhler2025promptbooks, debelak2025embeddings, abdurahman2025primer.
- **Silicon samples remain the most disputed subfield**: The optimistic starting point is argyle2023out, with sun2024random extending subgroup simulation. But later evidence finds serious limits in persona prompting, demographic alignment, entropy structure, and behavioral validity. Representative sources: argyle2023out, sun2024random, bisbee2024synthetic, dominguezolmedo2024questioning, gao2025caution.
- **Bias and downstream inferential error are now a central concern**: More recent work shows that even when annotation accuracy looks respectable, model-specific directional bias or prompt sensitivity can distort substantive conclusions. Representative sources: weidmann2026democracy, baumann2025hacking, mclaren2026magic.

## Tensions / debates
- **Replacement versus augmentation**: Optimistic studies suggest LLMs can replace crowd workers and sometimes expert coders on specific tasks (gilardi2023chatgpt, tornberg2025outperform). More cautious studies argue they are better treated as augmenting human workflows than as universal substitutes (ziems2024transform, heseltine2024substitute, ornstein2025stochastic, halterman2025codebook).
- **Are silicon samples promising or fundamentally misleading?**: Argyle and Sun present LLM-based human-subpopulation simulation as feasible under some conditions (argyle2023out, sun2024random). Bisbee, Dominguez-Olmedo, and Gao push the field toward skepticism by documenting failures in public-opinion recovery, survey entropy, and behavioral replication (bisbee2024synthetic, dominguezolmedo2024questioning, gao2025caution).
- **Accuracy versus inferential validity**: Much of the early literature emphasizes label accuracy. The newer critique is that good-looking annotation scores do not guarantee stable downstream inference when prompts or model configurations vary (baumann2025hacking, mclaren2026magic).

## Gaps
There is still no settled social-science reporting standard analogous to CONSORT or STROBE for LLM-based measurement. The field has primers and emerging checklists, not a consensus protocol (abdurahman2025primer, mclaren2026magic). Evidence is also thinner for non-English long-form texts, multimodal data, confidential administrative data, and longitudinal robustness under model updates. Finally, only a small slice of the literature explicitly links annotation error to downstream substantive inference rather than to benchmark accuracy alone (baumann2025hacking is the clearest exception).

## PENDING
- **Benoit, Kenneth; De Marchi, Scott; Laver, Conor; Laver, Michael; Ma, Jinshuai. 2026. _Using large language models to analyze political texts through natural language understanding_. American Journal of Political Science. DOI: 10.1111/ajps.70050.**
  - Mentioned in: AJPS article page summaries and secondary institutional metadata.
  - Why relevant: It appears to be a major 2026 political-methods contribution on natural-language understanding for political texts.
  - What I could not verify: I confirmed metadata and DOI, but I could not reliably access the full primary abstract/article text in this session, so I did not summarize its substantive claims.

## Process notes
- Screened about 45 candidate records/pages and returned 20 verified sources plus 1 PENDING item.
- Stopping signal: by the last search rounds, both number and type had saturated. New searches mostly rediscovered the same core venues (Political Analysis, Research & Politics, PSRM, Sociological Methods & Research, AMPPS, PNAS, arXiv) and added only marginally adjacent tutorials or domain-specific applications rather than genuinely new subthemes.
- I did not pursue pure NLP benchmark papers, engineering papers on model architectures, or general AI-in-science discussions beyond directly relevant anchor material, because the strand definition excludes them.
- Scope interpretation: I treated “LLMs as research methods” to include text classification, coding, information extraction, scaling open-ended responses, and silicon-sample / LLM-as-respondent work, while excluding agentic workflow assistance and generic writing-support uses.