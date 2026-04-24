---
name: validate-construct
description: Stress-tests whether an operationalized indicator captures the conceptual construct it claims to measure. Runs convergent, discriminant, content, and face validity checks and surfaces specific threats. Assumes prior /conceptualize and /operationalize outputs; produces a construct-validity file.
---

# /validate-construct — does the indicator measure the concept?

Construct validity is the hardest form of validity to assess and the easiest to pretend you have. This skill forces the question explicitly: does this specific indicator, under this specific coding rule, measure the concept as defined in the conceptualization file?

The skill is structured around the four classical construct-validity checks — convergent, discriminant, content, and face — each with its own failure mode.

## When to use

- You have just operationalized a construct (via `/operationalize`) and want to stress-test the indicator before committing to it.
- You are evaluating an indicator proposed by a prior study or a secondary dataset.
- You are responding to a reviewer who has flagged a measurement concern.

## Do not use when

- No operationalization exists. Run `/operationalize` first.
- The indicator is a direct, uncontested measure (age, vote share). Construct validity is trivially satisfied.
- The concern is replicability of the measurement process across time or coders. Use `/assess-reliability`.

## The interview

Walk each indicator in `docs/operationalization.md` through four checks:

1. **Convergent validity.** *"Does this indicator correlate with other accepted measures of the same concept?"* Name those other measures. Compute or cite correlations. If no accepted alternative exists, acknowledge it — this is a construct whose validity rests almost entirely on content and face checks.

2. **Discriminant validity.** *"Does the indicator distinguish the concept from adjacent concepts it should be separable from?"* Pull the `neighbors` list from `docs/conceptualization.md`. For each neighbor, ask whether the indicator would confuse the two. A "state capacity" measure that correlates 0.95 with GDP per capita has a discriminant problem.

3. **Content validity.** *"Does the indicator cover every dimension identified in the conceptualization?"* Compare against the `dimensions` block of `docs/conceptualization.md`. If any dimension is unmeasured or underweighted, flag it. Content-validity gaps often masquerade as "we focused on the most important dimension" — force the researcher to defend that framing.

4. **Face validity.** *"If you showed this indicator + coding rule to three domain experts, would they recognize it as measuring your concept?"* This is the weakest check but the easiest to run. A "no" from face validity is usually a signal that something upstream is wrong.

5. **Specific threats.** *"What are the two or three most plausible mechanisms by which this indicator would diverge from the concept?"* Demand specific alternative explanations, not generic caveats. Each threat becomes a candidate for downstream robustness work.

## Failure modes

- **Validity by assertion.** The researcher claims construct validity without naming alternative measures or adjacent concepts. Force specificity on both.
- **Using a proxy as the criterion.** The researcher validates the indicator against another imperfect measure of the same concept and treats the correlation as validity. Flag the shared measurement error.
- **Content coverage pretended.** A single item is asserted to cover a multi-dimensional concept. Compare to the conceptualization file; if dimensions are unmeasured, say so.
- **Face validity only.** The researcher rests the case entirely on "it looks right to me." This is necessary but not sufficient; demand at least one other check.
- **Generic caveats.** "Of course every measure has limitations." Useless. Threats must name specific mechanisms the researcher could in principle test or bound.

## Output

Produce `docs/validity-construct.md` with:

```yaml
indicator: "<reference to operationalization block>"
convergent:
  alternative_measures: ["<measure 1>", "<measure 2>"]
  correlation_or_assessment: "<numeric or narrative>"
  verdict: "<strong | weak | untestable>"
discriminant:
  neighbors_checked: ["<concept 1>", "<concept 2>"]
  separation_assessment: "<narrative>"
  verdict: "<strong | weak | problematic>"
content:
  dimensions_in_conceptualization: ["<dim 1>", "<dim 2>"]
  dimensions_covered_by_indicator: ["<dim 1>"]
  gaps: "<if any>"
face:
  expert_check_plan: "<who would vet this>"
  verdict: "<passed | needs work>"
threats:
  - mechanism: "<specific way the indicator could diverge from concept>"
    bound_or_test: "<how to check>"
```

Log the session to `interaction-log.csv` noting the indicator validated and the path to the output file.

## Handoff

After `/validate-construct`, invoke `/validate-criterion` to assess the indicator against external criteria (concurrent or predictive). Treat construct validity as the more philosophical check and criterion validity as the more empirical one; both belong in the dossier.

## Explicit non-claims

Construct validity cannot be proven, only defended. This skill surfaces the defense; the researcher decides whether it is strong enough for the argument at hand.
