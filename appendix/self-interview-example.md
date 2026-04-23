# Self-Interview Worked Example: Designing a Survey Questionnaire

A concrete illustration of the prompt-level self-interview described in \S3.4 of *With Great Powers*. The task is deliberately domain-standard rather than paper-specific: a survey questionnaire with an embedded information-provision experiment, the kind of instrument a political-behavior or public-opinion researcher builds several times a year. The transcript below is condensed for display; the live session ran longer and included short follow-up clarifications on most items.

## Setup

The researcher opens a fresh agent instance and starts with a minimal framing prompt — not a full specification. The point is to make the agent interview her, not to produce a plan she has already written.

> I need to design a survey questionnaire on AI adoption among academic social scientists, with an embedded information-provision experiment. Before you draft any items, interview me: ask one question at a time about each aspect of the design you would need to specify before writing. Do not assume defaults. Wait for my answer before moving on.

## The interview

The eight questions below are the ones the agent asked in order. Each is a decision the researcher's domain knowledge strictly dominates a model default on, and each is load-bearing for the instrument's validity.

1. **Population, sampling frame, and mode.** Who exactly are the respondents — a specific professional society's member list, a commercial panel, departmental contacts? What is the mode (web, phone, in-person) and what is the field period?
   — *Researcher:* Members of three professional associations; web-only via Qualtrics; two-week field period opening on a Monday.

2. **Constructs and measurement.** Which dimensions of "adoption" are in scope — behavioral frequency, tool familiarity, attitudes, perceived norms? For each, do you want to use an existing validated scale where one exists, or write discipline-specific items?
   — *Researcher:* Behavioral (past-30-day use by research task), attitudes (approval and concern), perceived norms. Published scales for attitudes; write new items for behavior because existing instruments don't map to research tasks.

3. **Experimental design.** What are the arms of the embedded experiment, what is the randomization unit, and which outcomes go pre- versus post-treatment? Do you want blocking on any pre-treatment covariates?
   — *Researcher:* Two arms (short factual statement on AI capability levels vs. control). Unit is the respondent. Demographics and prior use pre-treatment; attitudes and policy items post-treatment. Block on discipline.

4. **Length budget and priority order.** What's the target median completion time, and which blocks would you cut first if we go over budget?
   — *Researcher:* 12 minutes median. Priority order: behavioral block, experiment, attitudes, norms, demographics. Drop norms first.

5. **Sensitive or politically loaded items.** Any items sensitive enough to warrant explicit non-response options, branching, or reverse-coded balance? Any items you want order-randomized to mitigate priming?
   — *Researcher:* Randomize order within the attitudes block. Offer "prefer not to answer" on institutional-affiliation items. No reverse coding needed on validated scales already balanced.

6. **Data-quality safeguards.** Which quality checks — attention checks, instructional manipulation checks, speeding and straight-lining flags, bot screens — should be built in, and where should they sit?
   — *Researcher:* One attention check mid-survey; one IMC after the experiment; speeding flag at one-third of median completion; reCAPTCHA at entry. No straight-lining flag — no grid items long enough to warrant it.

7. **Pre-registration and codebook.** Are we pre-registering the instrument and the experiment's hypotheses? Should the deliverable include a codebook with stable item IDs so analysis code can reference them?
   — *Researcher:* Yes, pre-register on OSF before fielding. Codebook with stable item IDs, one row per item, with variable labels ready to reuse in Stata.

8. **Output formats and sign-off gates.** What should the final artifact be — a Qualtrics QSF, a plain-text item bank for import, a LaTeX appendix version for the pre-registration, or all three? Who signs off before fielding, and how many pilot waves?
   — *Researcher:* QSF, LaTeX for the pre-registration, and a CSV codebook. Two pilot waves, N=10 cognitive and N=50 quantitative, each with explicit sign-off before the next.

## What the interview produced

The eight questions moved the prompt from "design a survey on AI adoption" to a plan that specifies: population and mode; which constructs use validated scales versus new items; the experimental arms, randomization unit, and pre/post covariate placement; length budget and a priority ordering for cuts; sensitivity handling and order randomization; data-quality checks and their placement; pre-registration commitment and codebook schema; deliverable formats and two-stage pilot sign-off.

Each of these is a decision the researcher would otherwise have delegated to the model implicitly — and, in most cases, one the model would have defaulted on silently rather than asked about.

## Why this structure

The questions are not a generic survey-methods checklist. They were selected under two filters:

- **Load-bearing.** Getting the answer wrong changes the validity of the instrument, not merely its polish.
- **Domain-dominant.** The researcher's answer strictly dominates a model default. Items the agent can reasonably default on — wording of validated scale items, response-option phrasing for standard demographics, ordering of attention-check wording — are deliberately absent. The budget is spent on decisions the agent should not make alone.

A self-interview that hits the load-bearing, domain-dominant decisions is short — five to eight questions is typical — and produces a prompt plan dense enough that the subsequent drafting session is mostly execution. The alternative, a long initial prompt written without the interview, tends to over-specify the easy decisions and under-specify the hard ones.
