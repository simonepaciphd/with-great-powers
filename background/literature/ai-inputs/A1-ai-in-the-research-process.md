# ai-in-the-research-process — Literature landscape

## Top 3 most relevant sources
1. abdurahman2025primer — Closest match to the paper’s thesis because it gives explicit evaluation criteria for LLM-based social-science research and centers validity, transparency, and replicability.
2. davidson2025integrating — Best broad methods map of the field, organizing the landscape around measurement, prompting, and simulation rather than around hype.
3. kozlowski2025simulating — Strongest single skeptical counterweight on why AI stand-ins should not be treated as human substitutes without serious validation.

## Themes identified
- **AI as research augmentation rather than wholesale replacement**: The most persuasive positive literature treats LLMs as tools for text analysis, coding, extraction, scaling, and workflow acceleration, not as autonomous researchers. Representative sources: bail2024generative, davidson2025integrating, ornstein2025stochastic, stuhler2025promptbooks, digiuseppe2026scaling.
- **Validation, documentation, and researcher control**: Several methods pieces converge on the view that LLM outputs should be treated as measurements that require benchmarking, transparent reporting of prompts/model versions, and retained human oversight. Representative sources: abdurahman2025primer, abdurahman2024perils, brickman2025assessment, broska2025mixed, lyman2025balancing.
- **Simulation and substitution debates**: A major subliterature asks whether LLMs can stand in for respondents or social actors. The most careful contributions either restrict such use or propose hybrid designs rather than direct replacement. Representative sources: horton2023homosilicus, manning2024automated, broska2025mixed, kozlowski2025simulating, bisbee2024synthetic.
- **Agentic AI for reproducibility and research infrastructure**: Recent work extends the debate from text coding to agentic reproducibility audits and code repair. The evidence is promising but clearly short of full automation. Representative sources: hu2025reprobench, shah2026automating, messing2026train, pepinsky2026agentic.
- **Institutional effects on publishing and disciplinary practice**: Another live theme is how AI may reshape manuscript production, peer review, and norms of acceptable assistance. Representative sources: munger2026peer, munger2026scenarios, messing2026train, alvero2026state.

## Tensions / debates
- **Augmentation vs. substitution**: Bail, Davidson and Karell, Ornstein et al., and Stuhler et al. emphasize augmentation of existing workflows, whereas Bisbee et al., Kozlowski and Evans, Lin, Wang et al., and Westwood argue that substituting models for humans often creates invalid or harmful inferences.
- **Helpful alignment vs. scientific fidelity**: Lyman et al. show that aligned models may be easier to use but less faithful to the behaviors researchers want to measure. This creates a direct tension between user-friendly agents and valid scientific instrumentation.
- **Promise of agentic infrastructure vs. present capability limits**: Brookings-style commentary and Pepinsky’s post suggest near-term workflow transformation, but REPRO-Bench and Shah et al. show that current agentic systems remain error-prone and require oversight.
- **Pragmatic adoption vs. norm-setting**: Munger’s publishing scenarios and Alvero et al.’s sociology survey both suggest growing use under unsettled norms. The literature is ahead on method experimentation and behind on shared disclosure standards.

## Gaps
The literature is much stronger on **LLMs as methods tools** than on **agentic AI as a fully integrated research collaborator**. There is still little peer-reviewed work on reporting standards for human-agent collaboration across the entire research pipeline, on division of labor between researchers and agents, or on documented cases where agentic systems materially shaped published social-science outputs from question formation through final manuscript. There is also more evidence on text and survey applications than on archival research, causal design, literature review, or theory development.

## PENDING
- **benoit2026nlu** — AJPS article on using LLMs to analyze political texts through natural language understanding. I verified the title, authors, venue, and DOI from secondary references, but I could not directly access the article text in-session because the publisher page was inaccessible. This looks highly relevant as a published political-science example to chase next.
- I did not silently drop other blocked sources: everything else that looked central was either verified directly or excluded as duplicative, off-scope, or too weak on provenance.

## Process notes
- Screened approximately 65 candidate hits across journals, working papers, institutional commentary, and researcher blogs; returned 23 entries total, of which 22 are verified and 1 is pending.
- I stopped when later search rounds mostly returned the same Sociological Methods & Research special-issue cluster, the same survey-substitution critiques, or commentary pieces without introducing new source types or themes. Diminishing returns were evident on both **number** and **type/theme**.
- I chose not to pursue generic computer-science “AI scientist” papers unless they were explicitly tied to social-science research practice or reproducibility.
- Scope interpretation: I treated “agentic AI in research practice” broadly enough to include workflow methods papers, human-subject substitution debates, reproducibility agents, and disciplinary governance/publishing discussions, but excluded vendor marketing and generic productivity advice.
