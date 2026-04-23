# llm-agents-as-research-infrastructure — Literature landscape

## Top 3 most relevant sources
1. piao2025agentsociety — Best direct infrastructure paper for this strand: it treats the simulator itself as a platform for surveys, interviews, interventions, and large-scale social experimentation.
2. ashery2025conventions — Strongest peer-reviewed substantive demonstration that interacting LLM populations can generate collective phenomena such as convention formation, critical-mass dynamics, and emergent bias.
3. larooij2025validation — Best critique of the field’s epistemic foundations, especially on calibration, operational validity, and the risk that generative ABM revives old ABM problems rather than solving them.

## Themes identified
- **Foundations and infrastructure**: The strand now has clear architectural anchors: Smallville/generative agents as the design precursor (park2023generative), Concordia as a reusable grounded simulation library (vezhnevets2023concordia), and AgentSociety as a large-scale social-simulation platform (piao2025agentsociety). Conceptual syntheses increasingly frame this as a distinct research paradigm rather than simple prompt engineering (haase2025paradigm, taillandier2025abss).
- **Collective phenomena and social dynamics**: The most developed application areas are norm emergence, polarization, and networked interaction. The strongest peer-reviewed example is convention formation in LLM populations (ashery2025conventions). Polarization work is moving toward hybrid human-agent settings rather than all-silicon societies (donkers2025polarization).
- **Economic, policy, and domain-specific societies**: LLM-agent simulations are being used to model macroeconomic dynamics, market behavior, and policy-relevant health decisions. EconAgent is the clearest peer-reviewed macro example (li2024econagent), while VacSim shows a policy-sandbox logic for intervention testing under explicit caveats (hou2025vaccine).
- **Validation and measurement**: The literature is increasingly aware that face-valid interaction is not enough. Work now ranges from person-grounded validation against real respondents (park2024people) to operational validation against platform traces (tomasevic2025operational) and targeted quality-control diagnostics for opinion simulation (neumann2026opinions).
- **Science-of-science and novel application spaces**: The field is branching into nonstandard social-science targets such as citation networks and simulated scholarly behavior (ji2026citation), suggesting that “social infrastructure” here includes systems for studying research communities themselves.

## Tensions / debates
- **Exploration versus evidence**: Many papers present LLM societies as exploratory sandboxes, but the validation literature argues that exploratory usefulness should not be confused with confirmatory evidence about humans. Compare piao2025agentsociety, hou2025vaccine, and ashery2025conventions with larooij2025validation, neumann2026opinions, and hullman2026behavioral.
- **Paradigm shift versus ABM extension**: Some authors describe generative social science as a new paradigm (piao2025agentsociety, haase2025paradigm), whereas others interpret it as an extension of classical ABM that should remain answerable to older validation and transparency standards (vezhnevets2023concordia, taillandier2025abss, larooij2025validation).
- **Capability versus fidelity**: Stronger reasoning does not necessarily produce better simulation. zhou2024fantasy shows unrealistic omniscient setups can inflate apparent success; andric2026mismatch argues that better strategic reasoning can make a model a worse behavioral sampler.

## Gaps
The literature is still thinner than some of the research questions assume. First, there are relatively few head-to-head comparisons between LLM-agent simulations and classical ABMs on the same substantive problem. Second, uptake evidence for frameworks is weak: most infrastructure papers are still authored by framework builders and evaluated on home-field cases. Third, collective action proper is less developed than polarization, norms, and social-media dynamics. Fourth, many “validation” exercises remain one-shot or domain-specific, with limited out-of-sample tests against real human collective behavior. Finally, standards for when simulated agents can support confirmatory inference are still emerging rather than settled.

## PENDING
No PENDING entries. I verified the sources included here and did not silently drop any inaccessible item that I intended to summarize. I did exclude several engineering-heavy multi-agent papers and general agent benchmarks because they lacked a clear social-science framing under this strand definition.

## Process notes
- Screened approximately 48 candidate items; returned 17 sources.
- Search proceeded in rounds: (1) anchor and infrastructure papers; (2) substantive applications by domain; (3) validation and critique; (4) follow-up on ABM-bridge and peer-reviewed venues; (5) saturation checks on markets, policy, and science-of-science.
- Diminishing returns appeared on **number** in the last two rounds, where most search results were duplicates, mirror pages, or minor variants of already captured papers. Diminishing returns also appeared on **type/theme**: late searches mostly yielded additional engineering papers, adjacent game-agent papers, or news coverage rather than genuinely new social-science subthemes.
- Scope interpretation: I treated the strand as multi-agent or agent-society work where agents are modeled as social actors or synthetic participants, plus directly relevant validation/critique papers. I excluded business-process agents, generic autonomous-agent engineering, and papers with no substantive social-science claim.
- Saturation is good but not absolute. The literature is moving fast in 2025–2026, so this should be treated as a strong current landscape rather than a permanently closed bibliography.