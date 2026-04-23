# ethics-environment-privacy — Literature landscape

## Top 3 most relevant sources
1. `aiindex2026report` — best single anchor because it synthesizes the current environment, privacy, adoption, labor, and governance landscape in one authoritative report.
2. `xiao2025netzero` — strongest quantitative adjacent source on AI-server energy, carbon, water, and concrete mitigation pathways.
3. `spectorbagdady2025integrity` — most directly aligned with the paper’s thesis because it frames generative-AI use in research as a prospective governance and transparency problem.

## Themes identified
- **Environmental footprint is now measurable, but disclosure remains weak**: the literature converges on rising electricity, water, and carbon burdens from frontier-model infrastructure, while stressing that measurement is constrained by poor developer disclosure. Representative sources: `aiindex2026report`, `iea2025energy`, `xiao2025netzero`.
- **Privacy risk spans the full model lifecycle**: relevant concerns are not just prompt-time leakage, but also web-scale data collection, memorization, regurgitation, and adversarial extraction. Representative sources: `king2026privacy`, `carlini2023memorization`, `nasr2025extraction`.
- **Research-context mitigation is moving toward governance, not just technical fixes**: the most useful adjacent sources emphasize PETs, controlled sharing, trusted intermediaries, explicit disclosure heuristics, and prospective integrity standards rather than vague calls for “responsible AI.” Representative sources: `oecd2025pets`, `oecd2025sharing`, `spectorbagdady2025integrity`, `jones2025qualitative`, `linardon2025eating`.
- **Societal-impact evidence is strongest on adoption, task productivity, and early labor effects**: uptake has been extremely rapid; narrow task-level productivity gains can be large; short-run aggregate labor-market effects appear smaller and slower; one recent RCT suggests AI can narrow education-based productivity gaps. Representative sources: `bick2024adoption`, `brynjolfsson2023work`, `humlum2025labor`, `cruces2026education`.
- **Democratic-discourse risks now have credible empirical evidence, but the literature is still thinner than labor/productivity work**: recent experiments show that LLM-generated policy messages and GPT-4 conversations can be persuasive under controlled conditions. Representative sources: `bai2025persuade`, `salvi2025gpt4`.

## Tensions / debates
- **Productivity gains versus labor-market transformation**: task-level experiments show meaningful gains (`brynjolfsson2023work`, `cruces2026education`), but short-run labor-market outcomes remain muted (`humlum2025labor`).
- **Openness versus confidentiality**: the data-sharing literature treats AI benefits as tied to wider access, but repeatedly qualifies that with privacy, IP, and control constraints; PETs and trusted intermediaries are the main compromise instruments. Sources: `oecd2025sharing`, `oecd2025pets`.
- **Technical mitigation versus workflow governance**: privacy research documents leakage risks (`carlini2023memorization`, `nasr2025extraction`), while research-integrity and methods pieces argue that disclosure, auditing, and ex ante standards are equally necessary (`spectorbagdady2025integrity`, `jones2025qualitative`, `linardon2025eating`).

## Gaps
The literature is thinner than the draft questions assume in three places. First, there is still very little direct empirical work on ordinary academic or social-science research workflows using confidential data (interview transcripts, fieldnotes, survey microdata, IRB-bound material); most strong privacy evidence comes either from foundation-model security work or sectoral guidance. Second, environment work is stronger on modeled trajectories than on audited vendor disclosure of training and inference footprints. Third, democratic-discourse and bias-amplification evidence exists, but it is not yet as cumulative or settled as the labor/adoption literature. For a brief §4.1 acknowledgment, that is enough; for a deeper sub-argument, it is not.

## PENDING
No unverified sources were retained. I verified that no candidate source was silently dropped into the narrative: inaccessible or weakly relevant items were excluded rather than summarized.

## Process notes
- Screened approximately 45 candidates across 6 search rounds; returned 17 verified sources.
- Diminishing returns appeared in rounds 5–6 on both number and type: new results were mostly repeats, close variants of already-returned labor/discourse papers, or generic AI-ethics commentary without better fit to the strand.
- I did not pursue vendor white papers, broad non-empirical commentary, or activism-only sources because the prompt explicitly deprioritized them.
- I resolved one scope ambiguity explicitly: I interpreted the privacy question narrowly as **research-data governance and confidentiality in LLM-mediated research workflows**, not as generic consumer-AI privacy. That interpretation best fits the paper’s thesis and keeps the strand usable for a brief responsible-acknowledgment section.
