# Gordon, Samii, Su — Data-NoMAD

**Full citation (provisional):** Gordon, Sanford; Samii, Cyrus; Su, [first name from PDF]. "Data-NoMAD: A Tool for Boosting Confidence in the Integrity of Social Science Survey Data." arXiv:2501.14651, January 2025.

**Primary URLs:**
- arXiv abstract: https://arxiv.org/abs/2501.14651
- HTML: https://arxiv.org/html/2501.14651v1
- ADS record: https://ui.adsabs.harvard.edu/abs/2025arXiv250114651G/abstract
- BITSS lightning-talk slides (Samii / Gordon): https://www.bitss.org/wp-content/uploads/2024/10/06d_Lightning-Talk_Data-NoMAD_Sanford-Gordon-Cyrus-Samii.pdf

**Verification:** partially-verified (summary from abstract + BITSS slides)

---

## What it is

Data-NoMAD = "Data Non-Manipulation Authentication Digest." A tool that lets researchers **certify** that a dataset has not been inappropriately manipulated between collection and public archival, and lets third parties **verify** the certification.

## Mechanism

- On initial download from a survey platform (current version: Qualtrics, SurveyCTO), Data-NoMAD computes a **column-wise SHA-256 hash digest** of the raw dataset.
- The digest is stored **before** legitimate transformations (anonymity-preserving redactions, etc.) are applied.
- Third parties can later re-hash an archived dataset; mismatches identify columns that have been deleted, added, or altered.

## Gap it fills

Complements, doesn't replace, existing replication-archive practices. Targets a specific failure mode: post-hoc manipulation of raw data between collection and archival — undetectable under current norms.

## Usable in the paper — **outline §3.3**

The outline explicitly references this work as motivation for the **interaction-log** feature of the project-setup protocol: "potential for encryption-based mechanism? Cite Gordon, Samii, and Su arxiv paper on Data-NoMad."

Framing for the paper:
- Data-NoMAD tackles **data integrity**; the interaction-log extension tackles **process integrity**.
- Same tooling philosophy: cheap cryptographic attestation enables third-party verification without trust.
- Candidate sentence: "Just as Gordon, Samii, and Su (2025) propose cryptographic attestation for raw-data integrity, agentic-AI workflows need analogous attestation for the human-agent interaction record that increasingly generates research artifacts."

## To verify when reading full PDF

- Exact author order and third author's first name.
- Whether the tool supports encrypted (vs. plain-hash) attestation.
- Whether they discuss extension beyond survey data.
