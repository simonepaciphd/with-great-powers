---
name: conceptualize
description: Moves a latent concept from vague invocation to a precise conceptual definition with dimensions, scope conditions, and explicit neighbors. The first step in a measurement workflow. Produces a conceptualization file that operationalization and validity skills build on.
---

# /conceptualize — from vague to precise

This skill does the upstream work that most projects skip. Before you can measure state capacity, efficacy, clientelism, or any other latent construct, the construct needs a precise definition, a clear set of dimensions, and explicit boundaries — what it is, what it is not, and under what conditions it applies.

The output is the intellectual foundation every downstream measurement choice rests on. Get this wrong and you will operationalize something other than what you intended to study.

## When to use

- You are opening a new project on a concept that is contested or under-specified in your target literature.
- You have inherited a concept and want to pin down what *you* are claiming it means, distinct from prior invocations.
- You have drafted text that uses a latent concept repeatedly and you suspect the definition has drifted.

## Do not use when

- The variable is directly observable and uncontested (age, vote share, turnout rate).
- A disciplinary gold-standard definition exists and you are deliberately adopting it as-is. Cite it and move on.
- You want to evaluate an existing measure. Use `/validate-construct`.

## The interview

1. **One-sentence working definition.** *"State your concept in a single sentence. What is it?"* Push for brevity. Vague definitions hide problems; precise ones surface them.

2. **Dimensions.** *"Is the concept unidimensional or multidimensional? If multidimensional, what are its dimensions?"* If the concept has parts (e.g., internal and external political efficacy), each dimension needs its own treatment downstream. If the researcher insists it is unidimensional, probe: *"Can you imagine cases that are high on one dimension and low on another?"* If yes, it is multidimensional.

3. **Scope conditions.** *"Under what conditions does this concept apply? Where does it stop being meaningful?"* Scope conditions distinguish serious conceptualization from kitchen-sink concepts. *"Clientelism" may not apply the same way in programmatic party systems; "state capacity" may not apply in failed states.*

4. **Neighbors and non-examples.** *"What is this concept \emph{not}? What adjacent concepts might be confused with it?"* Force the researcher to articulate boundaries. The concept should distinguish cases the researcher believes are genuinely different.

5. **Prior literature.** *"Which existing definitions are you building on, and where do you depart?"* Name anchor citations. A definition with no genealogy is a red flag.

## Failure modes

- **Circular definition.** The definiens restates the definiendum ("state capacity is the capacity of states to..."). Rework.
- **Kitchen-sink concept.** The concept absorbs any phenomenon the researcher finds interesting. Cut dimensions that do not pass the "imagine a case high on this, low on others" test.
- **Definition by measure.** The researcher defines the concept as whatever the available data can capture. Conceptualization must precede operationalization; invert this and validity threats become invisible.
- **No scope conditions.** The researcher assumes the concept applies universally. Ask for the limits explicitly.
- **Borrowed definition without ownership.** The researcher cites someone else's definition without saying whether they adopt it, modify it, or reject it.

## Output

Produce `docs/conceptualization.md` with:

```yaml
concept: "<name>"
one_sentence_definition: "<working definition>"
dimensions:
  - name: "<dimension 1>"
    gloss: "<one-line explanation>"
  - name: "<dimension 2>"
    gloss: "<one-line explanation>"
scope_conditions: "<when the concept applies; when it does not>"
neighbors:
  - concept: "<adjacent concept>"
    distinction: "<what separates them>"
prior_definitions:
  - source: "<author, year>"
    relationship: "<adopt | modify | reject>"
    note: "<short rationale>"
```

Log the session to `interaction-log.csv` noting the concept conceptualized and the path to the output file.

## Handoff

After `/conceptualize`, invoke `/operationalize` to translate each dimension into a measurable indicator. The conceptualization file is the reference downstream skills cite when justifying indicator choices.

## Explicit non-claims

This skill does not settle conceptual disputes in a literature. It forces the researcher to state a precise position and own it. Substantive definition remains the researcher's call.
