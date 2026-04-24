---
name: validate-criterion
description: Assesses criterion validity — concurrent and predictive — by comparing the indicator against an external gold standard or expected outcome. Assumes prior /conceptualize, /operationalize, and /validate-construct outputs. Produces a criterion-validity file.
---

# /validate-criterion — does the indicator behave as it should?

Criterion validity asks a narrower, more tractable question than construct validity: does the indicator correlate with things it *should* correlate with, and not with things it *should not*, given what the concept is supposed to predict?

Two flavors: *concurrent* (agreement with a gold-standard measure at the same time point) and *predictive* (agreement with an outcome the concept should cause or precede). A third relative, *known-groups validity*, checks whether the indicator discriminates between groups theory says it should discriminate between.

## When to use

- After construct-validity work, when you want a specific empirical check on the indicator.
- When a plausible criterion measure or outcome exists — a gold standard, an expert rating, a downstream behavior.
- When a reviewer has asked whether the measure "does what it should."

## Do not use when

- No plausible criterion exists — the concept is so foundational that nothing external is an appropriate benchmark. Say so in the dossier and move to `/assess-reliability`.
- The construct is defined in a way that makes criterion validity circular (e.g., when the supposed criterion is just another indicator of the same thing).
- Construct validity is not yet assessed. Run `/validate-construct` first — criterion validity without construct validity is a thin defense.

## The interview

1. **Concurrent criterion.** *"Is there a gold-standard measure of the same concept, at the same time point, that you can compare against?"* Expert ratings, hand-coded samples, a high-cost measure used as a benchmark for a low-cost one. If yes: what correlation would be strong enough to count as agreement? If no: acknowledge and move on.

2. **Predictive criterion.** *"What outcome should this indicator predict if it is measuring what you think it is?"* State the prediction *before* running the check. A measure of "state capacity" should predict service delivery; a measure of "efficacy" should predict turnout controlling for covariates.

3. **Known-groups validity.** *"Are there groups — countries, cohorts, regimes, time periods — that theory says should score systematically differently on this indicator?"* If yes: does the indicator separate them? If the known-groups contrast fails, something is wrong upstream.

4. **Effect-size threshold.** *"What correlation or difference would you treat as evidence of validity, and what would you treat as evidence against?"* Lock this in before running the check. Post-hoc rationalization of small correlations as "modest but meaningful" is a validity-assessment failure mode.

5. **The criterion's own validity.** *"What are the known validity threats of the criterion measure itself?"* No criterion is pure. A WGI-benchmarked indicator inherits WGI's measurement issues. Document the criterion's own weaknesses so they travel with the dossier.

## Failure modes

- **Circular criterion.** The criterion is another operationalization of the same concept; agreement demonstrates nothing about construct validity. Catch this at step 1.
- **Post-hoc threshold.** The researcher decides after seeing the result whether the correlation is strong enough. Lock the threshold in step 4.
- **Cherry-picked prediction.** The researcher names many possible predictions and reports the one that worked. Require the prediction register in step 2 and document all checks run.
- **Criterion assumed infallible.** The gold standard is treated as error-free. Every criterion has its own validity issues; step 5 forces the acknowledgment.
- **Known-groups failure ignored.** The indicator fails to separate groups it should separate, and the researcher explains it away. That is a red flag; document it and consider whether the construct validity case survives.

## Output

Produce `docs/validity-criterion.md` with:

```yaml
indicator: "<reference to operationalization block>"
concurrent:
  criterion_measure: "<gold standard name or 'none plausible'>"
  correlation: "<numeric or 'n/a'>"
  threshold_set_beforehand: "<what strong agreement would have meant>"
  verdict: "<agrees | diverges | untestable>"
  criterion_own_threats: "<known weaknesses of the criterion itself>"
predictive:
  predicted_outcome: "<what the indicator should predict>"
  threshold_set_beforehand: "<minimum effect size that would count>"
  result: "<numeric or narrative>"
  verdict: "<predicts | fails | mixed>"
known_groups:
  groups_contrasted: ["<group A>", "<group B>"]
  expected_direction: "<narrative>"
  observed_direction: "<narrative>"
  verdict: "<discriminates | fails | partial>"
overall_assessment: "<narrative summary tying the three checks together>"
```

Log the session to `interaction-log.csv` noting the indicator validated and the path to the output file.

## Handoff

After `/validate-criterion`, invoke `/assess-reliability` to quantify measurement error across occasions, coders, or items. Validity without reliability does little; reliability without validity does nothing.

## Explicit non-claims

Criterion validity tests whether the indicator behaves as it should — not whether the concept is well-defined (that is conceptualization) or the indicator captures the concept (that is construct validity). Treat the three as complements; none substitutes for the others.
