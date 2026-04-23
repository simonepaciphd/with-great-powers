# control-and-research-decision-ownership — Literature landscape

## Top 3 most relevant sources
1. pepinsky2026agentic — Most directly aligned with the strand’s core claim for social science: agentic AI is useful for rule-following execution, but not for interpretation or argument.
2. halterman2026codebook — Best direct empirical-methods paper on when LLM delegation fails social-science operationalization and how to evaluate or improve it.
3. siebert2023meaningful — Strongest bridge from normative “human control” claims to actionable design properties that can be translated into research workflow checkpoints.

## Themes identified
- **Rule-following versus interpretation**: The clearest boundary in this literature is between delegable execution and nondelegable interpretation. Pepinsky frames this explicitly; Halterman and Keith show why background concepts and systematized constructs can diverge; Ashwin et al. show that coding errors can be systematically biased rather than random. Representative sources: pepinsky2026agentic, halterman2026codebook, ashwin2025bias.
- **Human control as workflow design, not a slogan**: HCI and AI-ethics work increasingly treats control as a design problem involving expectation-setting, intervention points, oversight, and contestability across the lifecycle. Amershi et al. provide general HCI guidelines; Davidovic differentiates the purposes of control; Siebert et al., Alfrink et al., and Yurrita et al. translate those ideas into operational properties and procedural needs. Representative sources: amershi2019guidelines, davidovic2023purpose, siebert2023meaningful, alfrink2023contestable, yurrita2023fairness, yurrita2025needs.
- **Delegation can work for bounded measurement tasks**: Several empirical studies find substantial upside for text annotation and measurement under constrained conditions. Gilardi et al. and Choi et al. show that LLMs can match or exceed crowdworkers or trained coders on some tasks, while Choi et al. show fine-tuning is especially powerful for complex expert-coded distinctions. Representative sources: gilardi2023annotation, choi2026expertcoding.
- **Transparency and epistemic authority become central once machines shape knowledge claims**: Palmer et al. argue opaque proprietary systems require explicit justification in academic research. Bartsch et al. and Hauswald theorize when technologies become epistemic authorities and what would justify deference to them. Representative sources: palmer2024proprietary, bartsch2025epistemic, hauswald2025artificial.

## Tensions / debates
- **Keep humans in charge vs. broader automation**: Pepinsky, Palmer, Davidovic, and Siebert argue for human ownership of interpretation, accountability, and control design. Lu et al. and Schmidgall et al. steelman the opposing view by presenting increasingly end-to-end automated research pipelines. Sources on each side: pepinsky2026agentic, palmer2024proprietary, davidovic2023purpose, siebert2023meaningful; lu2024scientist, schmidgall2025agentlab.
- **Zero-shot convenience vs. validity and reproducibility**: Gilardi and Choi show real gains from LLM coding, but Bisbee, Ashwin, and Halterman show that apparent performance can mask failures in variance, construct validity, or bias. Sources on each side: gilardi2023annotation, choi2026expertcoding; bisbee2024synthetic, ashwin2025bias, halterman2026codebook.
- **Contestability as post hoc appeal vs. lifecycle governance**: Lyons conceptualizes contestability, while Alfrink and Yurrita push toward lifecycle design, procedural needs, and public-sector implementation. Sources: lyons2021contestability, alfrink2023contestable, yurrita2025needs.

## Gaps
The literature is much stronger on annotation and coding than on higher-order research decisions. There is very little direct empirical evidence on delegating question formulation, theoretical framing, specification search, interpretation of results, or final substantive prose in social science. There is also little research on academic workflow mechanisms such as approval gates, audit logs, and contestability procedures inside actual research teams. STS-adjacent work on epistemic authority is conceptually rich, but it rarely studies concrete human-agent research collaboration. Conversely, empirical LLM-methods papers rarely engage deeply with STS or social epistemology.

## PENDING
No PENDING entries. I checked for highly relevant inaccessible items and did not silently drop any source that appeared central to this strand after the final verification pass.

## Process notes
- Screened approximately 45 candidate sources across repeated web-search rounds; returned 18 verified sources.
- Stopping signal: by the last two rounds, results were mostly repeats within already-covered clusters (contestability/HCI design, political-text annotation, epistemic-authority theory) and did not add new source types or sub-themes. Diminishing returns appeared on both number and type.
- I did not pursue broader AI-safety, general governance, or domain-specific medicine/law oversight literatures because the brief explicitly excluded most of that material unless it mapped back to research practice.
- Scope interpretation: I treated the strand as a cross-literature review of who should own research decisions when AI is in the pipeline, combining social-science methods papers, HCI oversight/contestability work, and social-epistemology/STS-adjacent theory.
