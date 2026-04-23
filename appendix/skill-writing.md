# Skill-Writing Protocol

A six-phase skill for writing a new skill: an interview-driven procedure that combines the researcher's existing practice with external sources to produce a reusable, named playbook that any agent instance can invoke.

Designed to compose with `project-setup.md` (skills are registered in `asset-registry.csv`) and `lit-review-protocol.md` (invoked as a subagent during Phase 2 when a skill needs external grounding).

Governing principles: **researcher control** and **radical transparency**. The agent never decides on its own what the skill should prescribe; the skill encodes the researcher's practice, not the agent's training-memory average. Every phase begins with an interview and waits for explicit sign-off before committing anything to disk.

---

## When to use

- A recurring research task keeps being re-specified from scratch in every new session.
- An existing skill is showing its age: the assumptions behind it have changed, or current best practice has moved beyond it.
- The researcher wants to institutionalize a preferred method so that multiple agent instances and subagents apply it consistently.
- A team or lab wants to share a common practice across projects and collaborators.

Do **not** start a new skill when the task is genuinely one-off, when an existing skill would cover the case with a small edit, or when the researcher has not yet formed a clear preference about how the task should be done. Skills are load-bearing documents; they should not be written speculatively.

## Artifacts the protocol produces

Under `C:\Users\spaci\Dropbox\Skills\` (global library) or `appendix/` of the active project (local, replication-bound):

1. `<skill-name>.md` — the skill itself, following the structure in the template at the end of this file.
2. A row in `asset-registry.csv` with `asset_type = reference` and creator flag (typically `mixed`).
3. A row in `interaction-log.csv` capturing the session that produced the skill.
4. Optional: supporting sources under `background/literature/` if Phase 2 pulled new references.

A skill installed globally is available to every project on the machine. A project-local skill is available only inside that project and travels with its replication package.

## Universal rules

1. **Interview first, draft second.** Every phase below has an interview step. Do not move to the drafting step of a phase until the researcher has answered the questions.
2. **Don't invent preferences.** If the researcher has not expressed a preference on a design question, mark the question `OPEN` in the draft and return to it. Do not fill gaps with plausible-sounding defaults.
3. **Mine artifacts, don't mine training memory.** The skill should encode this researcher's practice as evidenced in their own prior work, not the genre-average practice the model has seen during training.
4. **Skills are living documents.** Version them, date them, and update them when practice drifts. A skill that has not been revised in six months should be read again before reuse.
5. **Tight scope beats broad scope.** A skill that covers one task well is more useful than one that tries to cover every adjacent task poorly. Split broad skills into composable smaller ones.

---

## Phase 0 — Identify the need

Goal: confirm that a new skill is actually the right response.

**Interview checklist:**

1. *"Describe the recurring task in one sentence."*
2. *"Is there an existing skill, template, or document that already covers part of this? If yes, should we extend that one instead of starting fresh?"*
3. *"Would this skill live in the global library (reusable across all projects) or only inside the current project?"*
4. *"What is the concrete trigger for invoking the skill? A keyword, a project type, a task shape?"*

**Action step:** write a one-paragraph scope statement. Get sign-off before continuing.

---

## Phase 1 — Gather artifacts from past practice

Goal: extract the researcher's existing approach from things they have already produced.

**Interview checklist:**

1. *"What are 3–6 past examples of you doing this task? Names, paths, or pasted-in text are all fine."*
2. *"Which examples represent best-case practice? Which represent failure modes to avoid?"*
3. *"Are there any examples I should explicitly not generalize from — one-offs, constrained cases, early-career work you have since revised?"*

**Action step:** dispatch a subagent (fresh context, scoped task) to read the approved artifacts and produce a structured extraction:

- Recurring moves (what does the researcher always do?)
- Recurring decisions (what choices come up every time?)
- Implicit rules (what does the researcher never do, even when it would be natural?)
- Worked example (one or two past artifacts annotated by the extraction agent)

Present the extraction back to the researcher for correction, before proceeding to Phase 2.

---

## Phase 2 — Gather background sources

Goal: ground the skill in external knowledge where that knowledge is load-bearing, without diluting the researcher's own practice with genre-average text.

**Interview checklist:**

1. *"Which external sources do you want the skill to cite or build on — textbooks, methods papers, prior skills in the library, external templates?"*
2. *"Do we need a full lit review on this task, or is a fixed list of anchor sources enough?"*
3. *"Are there external templates you explicitly do not want to copy from?"*

**Action step:** if a lit review is needed, invoke `lit-review-protocol.md` as a subagent with the single strand defined here. Otherwise, read the anchor sources directly and extract the subset of external rules that should make it into the skill.

Keep extracted external rules clearly distinguishable from the researcher's own practice. Internal practice is the source of truth; external sources are the scaffolding.

---

## Phase 3 — Polish-the-skill interview

Goal: surface preferences, constraints, and default judgments that the artifacts and external sources did not settle.

**Interview checklist:**

1. Walk through the structured extraction from Phase 1 and ask: *"Is this rule right? Should it be stronger, weaker, or conditional?"*
2. *"On the open questions from Phases 0–2, how should the skill resolve them?"*
3. *"When this skill is invoked, when should the agent pause and ask the researcher, and when should it proceed?"*
4. *"What is the review cadence — should the agent interrupt after each phase, at the end, or both?"*
5. *"What explicit anti-patterns should the skill warn against? These are often the most useful part of a skill."*

**Action step:** revise the scope statement, the rule list, and the anti-patterns list with the researcher's answers.

---

## Phase 4 — Draft the skill

Goal: produce the `<skill-name>.md` file, following the template below.

**Action step:** assemble the skill in this order:

1. Title + one-paragraph description.
2. Composition notes (which skills it calls, which skills it is called by).
3. Governing principles (if the project has any).
4. "When to use" + "Do not use when" blocks.
5. Artifacts the skill produces.
6. Universal rules (numbered, short, enforceable).
7. Phases, each with an interview checklist and an action step.
8. A template or file skeleton when the skill produces a structured artifact.
9. Handoff with other skills.
10. Common failure modes.
11. Worked example (at minimum, a toy invocation).

Write the skill in the second-person imperative ("ask the researcher...", "do not commit..."), not the first-person descriptive ("I will ask..."). The voice is that of a protocol, not a narrator.

---

## Phase 5 — Test and iterate

Goal: the first real invocation is the final phase of drafting.

**Action step:**

1. Run the skill on one real task end to end.
2. Log where the agent paused unnecessarily, where it should have paused and did not, where the prescribed rules produced friction, and where the researcher had to manually intervene.
3. Revise the skill. First-draft skills that are never tested tend to ossify with silent flaws.

**Review cadence:** after the first three invocations, re-read the skill and decide whether to simplify, extend, or split. After every six months, schedule a re-read even without new invocations.

---

## Skill file skeleton

```
# <Skill Name>

<One-paragraph description: what the skill does, who it is for,
what it composes with.>

Governing principles: <if applicable>.

---

## When to use

- <trigger 1>
- <trigger 2>

Do not use when: <anti-triggers>.

## Artifacts the skill produces

1. <file or row>
2. ...

## Universal rules

1. <rule>
2. <rule>

---

## Phase <N> — <name>

Goal: <one sentence>.

**Interview checklist:**
1. *"<question>"*
2. *"<question>"*

**Action step:** <what the agent does after the interview>.

---

## Handoff with other skills

- <skill> reads/writes <artifact>
- ...

## Common failure modes

- <failure mode>: <how to recognize and recover>
- ...

## Worked example

<One concrete invocation, from trigger through artifact.>
```

---

## Handoff with other skills

- `project-setup.md`: a new skill's `.md` file is registered in `asset-registry.csv` per Rule 4 of the setup protocol; the session that produced it is logged in `interaction-log.csv` per Rule 5.
- `lit-review-protocol.md`: called as a subagent during Phase 2 when the skill needs external grounding beyond the researcher's anchor sources.
- `paper-writing-protocol.md`: consumed by skills that produce prose artifacts (to match voice and style).
- Any future skill: may itself call this skill-writing protocol when it is first drafted.

## Common failure modes

- **Training-memory skills.** The skill reads as a textbook summary rather than as this researcher's practice. Symptom: rules are generic and could apply to anyone in the field. Recovery: rerun Phase 1 with more artifacts; cut rules that are not traceable to a specific artifact or a specific answer from Phase 3.
- **Over-broad scope.** The skill tries to cover every adjacent case and ends up under-specifying each. Symptom: every invocation requires the researcher to re-scope the task. Recovery: split the skill into two or three narrower skills.
- **Missing anti-patterns.** A skill without explicit anti-patterns tends to drift toward genre-average output. Symptom: the agent produces plausible but wrong results confidently. Recovery: add a "Common failure modes" block with concrete symptoms and recovery steps (this section is the model).
- **Never tested.** The skill was drafted, saved, and never invoked. Symptom: on first real use, several rules produce friction or ambiguity. Recovery: Phase 5 is not optional.
- **Orphaned skills.** A project-local skill that was never synced to the global library when it proved reusable, or a global skill that was never migrated to a project's appendix when it became replication-bound. Symptom: the same skill exists in multiple places with drifted content. Recovery: declare one location canonical; periodic audit.

## Worked example

A diff-in-differences skill (the one gestured at in Figure~2 of the *Transparent Control* paper) was drafted by:

1. *Phase 0:* the researcher confirmed the task came up in roughly half their empirical projects and wanted a single reusable protocol.
2. *Phase 1:* three prior diff-in-diff analyses were handed to a subagent, which extracted recurring choices (two-way fixed effects vs. event-study; clustered vs. wild bootstrap; parallel-trends diagnostics as plots vs. placebo tests).
3. *Phase 2:* a narrow lit-review strand picked up the methods-text specification (Callaway-Sant'Anna, de Chaisemartin-D'Haultfœuille) without dragging in a full literature review.
4. *Phase 3:* the researcher answered that parallel-trends should default to event-time plots, and that clustering is always at the treatment-assignment level unless flagged.
5. *Phase 4:* the skill was written with three phases (specify, estimate, diagnose) and an explicit anti-pattern warning against hiding pre-trend violations behind reassuring averages.
6. *Phase 5:* first real invocation surfaced that the skill did not handle staggered adoption; the skill was revised to split into basic vs. staggered variants.

Total time: about two hours of researcher attention, distributed across a day.
