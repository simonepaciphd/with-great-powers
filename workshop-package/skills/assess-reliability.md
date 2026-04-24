---
name: assess-reliability
description: Quantifies measurement error across time (test-retest), coders (inter-rater), and items (internal consistency). The final step of a measurement workflow. Produces a reliability file that closes out the measurement dossier.
---

# /assess-reliability — how much noise in the measure?

Reliability is the easier sister of validity: it is quantifiable, it has standard statistics, and its absence is often the first red flag a reviewer catches. This skill walks the three classical reliability checks — test-retest, inter-rater, internal consistency — and forces the researcher to pick estimators, thresholds, and error-source diagnoses explicitly.

## When to use

- After construct and criterion validity work, when you need to quantify measurement error and its sources.
- When the indicator involves human or agent coding of text, behavior, or qualitative material.
- When the measure comes from multi-item scales and internal consistency is load-bearing.
- When the measure is expected to be stable over time and a repeated-measure opportunity exists.

## Do not use when

- The measure is a single deterministic observation with no plausible source of measurement error (administrative records of discrete events). Reliability is trivially high; note and move on.
- The pilot data is too thin to estimate any reliability coefficient meaningfully. Flag as a design gap and plan the needed data collection.
- The concern is validity, not reliability. A high-reliability invalid measure is worse than a low-reliability valid one.

## The interview

1. **Test-retest.** *"Should this indicator be stable over short time periods? If yes, what is the plan to measure stability?"* For survey items, a panel or re-interview. For content-coded text, repeated coding of the same passage after a delay. State the expected retest correlation and what would count as a failure.

2. **Inter-rater reliability.** *"If humans or agents coded this, what is the agreement statistic across coders?"* For categorical codes, Cohen's kappa or Krippendorff's alpha. For continuous, ICC. Name the coders (human, agent, or both), the double-coded subsample size, and the target threshold (conventional: kappa > 0.7; alpha > 0.8). If the indicator was coded by a single agent, flag that explicitly — single-agent coding has no inter-rater reliability check by construction.

3. **Internal consistency.** *"For multi-item scales, what is Cronbach's alpha or omega?"* Report both if possible; omega is more defensible for multidimensional scales. State the threshold before running the estimate. For unidimensional scales, factor analysis to confirm one-factor structure.

4. **Sources of measurement error.** *"Where is the noise coming from? Mode (web vs. phone vs. in-person), time of day or year, coder experience, item wording, respondent fatigue?"* Identify the plausible sources and whether they are addressable by design changes or only by statistical modeling.

5. **Reliability-vs-validity trade-offs.** *"Is there a reliability improvement that would cost validity?"* E.g., restricting item wording to the most reliable variant might narrow content coverage. Flag this explicitly.

## Failure modes

- **Alpha worshipped.** A high Cronbach's alpha is treated as evidence of validity. It is not; alpha is internal consistency, nothing more.
- **Single-coder blind spot.** Agent-coded or single-researcher-coded data is presented without an inter-rater check. If no double-coding exists, either plan it or document the limitation.
- **Post-hoc threshold.** Thresholds chosen after seeing the estimate. Lock thresholds in each step before estimation.
- **Ignoring time-varying error.** Test-retest is skipped because the researcher assumes the construct is stable. If the theory does not predict stability (or allows for drift), test-retest is not the right check — but say so.
- **Reliability as a virtue terminal.** Maximizing reliability at the cost of construct coverage or scope. A highly reliable measure of a narrow slice is often a less useful measure than a moderately reliable measure of the full concept.

## Output

Produce `docs/reliability.md` with:

```yaml
indicator: "<reference to operationalization block>"
test_retest:
  applicable: "<yes | no | n/a>"
  plan_or_estimate: "<numeric correlation + sample + time gap, or plan>"
  threshold_set_beforehand: "<what strong stability would mean>"
  verdict: "<stable | drifts | untestable>"
inter_rater:
  coders: "<human | agent | both>"
  double_coded_n: "<sample size>"
  statistic: "<kappa | alpha | ICC>"
  value: "<numeric>"
  threshold_set_beforehand: "<conventional or project-specific>"
  verdict: "<acceptable | low | untestable>"
internal_consistency:
  applicable: "<yes | no>"
  estimator: "<alpha | omega | factor analysis>"
  value: "<numeric>"
  threshold_set_beforehand: "<conventional or project-specific>"
  verdict: "<acceptable | low | n/a>"
error_sources_identified: ["<mode>", "<coder>", "<item wording>", "<respondent fatigue>"]
reliability_validity_tradeoffs: "<narrative>"
```

Log the session to `interaction-log.csv` noting the indicator assessed and the path to the output file.

## Handoff

`/assess-reliability` is the last structured step in the measurement workflow. The dossier in `docs/` — `conceptualization.md`, `operationalization.md`, `validity-construct.md`, `validity-criterion.md`, `reliability.md` — is now complete. Optionally invoke `/btw` for a welfare-check reflection on the session itself.

## Explicit non-claims

Reliability is not validity. A reliable measure of the wrong thing is still wrong. This skill quantifies noise; it does not adjudicate what the measure means. The researcher retains that judgment.
