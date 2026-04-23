# Spirling on open-source LLMs for replicability

**Author:** Arthur Spirling (Class of 1987 Professor of Politics, Princeton)

**Primary sources:**
- Princeton CSML profile / advocacy piece: https://csml.princeton.edu/news/arthur-spirling-advocating-replicability-research-using-language-models
- "Replication for Language Models: Problems, Principles, ..." (Barrie, Palmer, Spirling): https://arthurspirling.org/documents/BarriePalmerSpirling_TrustMeBro.pdf
- Nature comment (co-authored): "Why open-source generative AI models are an ethical way forward for science" (2023): https://www.nature.com/articles/d41586-023-01295-4
- Stanford Political Science talk (2026): "Large Language Models: Replications, Robustness, and Verification for Social Science"
- Yale ISPS talk (Nov 2025): "Large Language Models: Replication and Robustness for Social Science"
- Papers page: https://arthurspirling.org/papers.html

**Verification:** partially-verified (web summaries; download PDFs before citing)

---

## Core argument

Replicability in LLM-using research is threatened by the use of proprietary/closed models. Researchers cannot inspect code or training data, cannot verify that "the same" model returns the same answers, and cannot be confident published findings will ever be reproducible.

## Empirical evidence

Iterated labeling tasks given to multiple LMs (GPT-4, Gemini, Llama) and crowdworkers over many months:
- Tasks included ideology coding of manifestos and protest-event classification.
- LMs can be very accurate against a gold standard **but show considerable variance over time** — the same prompt-model combination drifts.

## Worst-case framing

"Political science building its knowledge base around published work that no one can replicate" — findings potentially resting on "random answers from inaccessible language models."

## Prescription

Open-source LLMs: inspect guts, customize, flag errors, community robustness over time.

## Usable in the paper

- **§3.1 (closed vs. open weights):** Spirling is the go-to citation. Combine with HAI 2026 data point on the performance gap: users face a real tradeoff (closed leads, but open is verifiable).
- **§4.2 (radical transparency / expanded replication package):** Spirling's normative frame directly supports the paper's argument for radical transparency at the research level.
- **§4.1 (reliability, p-hacking risk):** time-variance finding strengthens the case for deterministic validation checks (outline §3.4).
