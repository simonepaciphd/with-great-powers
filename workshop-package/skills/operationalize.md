---
name: operationalize
description: Translates a conceptual definition of a latent construct into a specific measurement strategy — concept-to-indicator mapping, unit of analysis, measurement scale, data source, and interpretive caveat. Assumes a prior conceptualization exists; produces a structured operationalization file that downstream validity and reliability skills consume.
---

# /operationalize — from concept to indicator

This skill converts theoretical language into measurement language. It assumes the conceptual work has been done (ideally via `/conceptualize`) and asks the researcher to make five decisions explicit for each construct: what indicator, at what unit, on what scale, from what data source, with what the indicator does not capture.

Every measure is imperfect. The skill refuses to pretend otherwise. The interpretive caveat is a first-class output, not an afterthought.

## When to use

- You have a conceptual definition of a latent construct (in `docs/conceptualization.md` or equivalent) and now need to decide how to measure it.
- You are picking among candidate indicators and want to surface the trade-offs before committing.
- You are writing a measurement section and want the operational choices documented in one place.

## Do not use when

- The concept has not been defined yet. Run `/conceptualize` first.
- The variable is a direct, uncontested measure (e.g., age in years, vote share). The skill is calibrated to latent constructs where operationalization is substantively contested.
- You want to evaluate an existing measure's validity. Use `/validate-construct` or `/validate-criterion`.

## The interview

Walk the researcher through each construct that needs measuring. For each one, pin down five items in order:

1. **Concept → indicator.** *"What concrete observable captures this concept?"* A concept is an abstract idea ("state capacity"); an indicator is a concrete measurement ("tax revenue as a share of GDP"). The mapping is never perfect. Push the researcher to articulate what the indicator captures well and what it misses.

2. **Unit of analysis.** *"Who or what is being measured?"* Individuals, households, organizations, country-years, events, texts. The unit must be consistent across the variables in the research design. If the theory operates at the individual level but the data is at the country level, flag the ecological inference problem.

3. **Measurement scale and coding.** *"Is this variable continuous, ordinal, categorical, or binary? How exactly will it be coded?"* For text data, what coding scheme. For survey data, what item wording. These decisions constrain what statistical or qualitative methods are appropriate later.

4. **Data source.** *"Where does the measurement come from?"* Specific dataset, survey instrument, administrative records, web scraping, experiment, interview protocol. "I will use survey data" is not specific enough; demand the survey, the wave, the population, the item.

5. **Interpretive caveat.** *"What does this measure not capture?"* Every measure is imperfect. Ask what aspects of the concept the indicator misses, what biases might be introduced, how these limitations affect interpretation. This caveat is a sign of sophistication, not weakness.

If the construct has multiple candidate indicators, run through the five items for each candidate, then ask the researcher to pick one (or to defend carrying more than one).

## Failure modes

- **Indicator-concept conflation.** The researcher treats the measure as identical to the concept. "GDP per capita" is not "development"; it is one indicator of one dimension. Flag and return to step 1.
- **Missing interpretive caveat.** The researcher presents an indicator without acknowledging what it misses. Ask step 5 again; do not accept silence.
- **Unit-of-analysis mismatch.** The theory operates at one level but the data is at another. Flag explicitly and ask whether the mismatch is manageable.
- **Vague data source.** The researcher names a category ("ANES", "survey data") rather than a specific instrument + wave + item. Push until the reference is uniquely resolvable.
- **Dead catalogue.** The researcher lists variables in a table without connecting each back to a conceptual dimension or a specific hypothesis. Every measure should trace to the construct it instantiates.

## Output

Produce `docs/operationalization.md` with one block per construct:

```yaml
construct: "<name>"
concept_reference: "<section in docs/conceptualization.md or source citation>"
indicator: "<specific observable measure>"
unit_of_analysis: "<individual | household | organization | country-year | event | text | other>"
scale: "<continuous | ordinal | categorical | binary>"
coding: "<precise coding rule>"
data_source: "<dataset + wave + item OR collection method specification>"
interpretive_caveat: "<what the indicator does not capture; biases introduced; how limitations affect interpretation>"
alternatives_considered: "<other indicators reviewed and why they were not chosen>"
```

Log the session to `interaction-log.csv` noting the construct(s) operationalized and the path to the output file.

## Handoff

After this skill runs, the natural next step is validity assessment. Invoke `/validate-construct` to stress-test whether the indicator captures the intended concept (convergent, discriminant, content validity). Then `/validate-criterion` for criterion validity. Then `/assess-reliability` for measurement error.

## Explicit non-claims

This skill does not pick the indicator for you. It surfaces the decisions and demands each one be made explicit and defensible. The researcher retains control over every substantive choice.
