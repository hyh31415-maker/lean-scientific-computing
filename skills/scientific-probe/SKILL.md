---
name: scientific-probe
description: Scientific research / 科研 workflow for hypothesis testing, mechanism discovery, simulations, numerical experiments, model comparison, replication, exploratory analysis, and audits of overengineered research code. Convert the scientific question into the smallest discriminating experiment and prevent premature frameworks, APIs, configuration systems, refactors, and productization. Do not use for ordinary production engineering, deployment, or UI/API delivery unless a scientific claim must first be tested.
---

# Scientific Probe

## Objective

Maximize expected information gain per unit of implementation complexity.

Treat code as experimental apparatus. The primary deliverable is evidence that changes confidence among competing hypotheses, not a polished software system.

Preserve data integrity, reproducibility, explicit assumptions, and honest uncertainty. Be bold in hypothesis generation and conservative in claims.

## 1. Classify the task before editing

Classify the task as one of:

- `PROBE`: test a new mechanism, explanation, effect, or mathematical claim.
- `REPLICATION`: reproduce or stress-test a reported result.
- `AUDIT`: identify engineering overhead that does not support a scientific inference.
- `MIXED`: a scientific question is embedded inside an engineering request.
- `ENGINEERING`: the user explicitly wants productionization, deployment, API/UI work, packaging, or long-term maintenance and no scientific inference is at issue.

For `MIXED`, isolate and run the scientific probe before designing the production system. For `ENGINEERING`, do not invent a scientific phase; follow the explicit engineering request.

## 2. Establish the research contract

Before writing or changing experimental code, state a compact research contract:

```text
Scientific question:
H0 / baseline explanation:
H1 / target explanation:
Relevant alternatives:
Discriminating observable or statistic:
Minimal experiment:
Decision rule fixed before the run:
Stop condition:
Assumptions that could invalidate the inference:
```

Do not substitute implementation milestones for this contract. “The pipeline runs” is not a scientific decision rule.

When the user has not supplied competing hypotheses, propose the smallest reasonable set. Mark them as working hypotheses rather than facts.

## 3. Separate hard constraints from soft assumptions

Treat these as hard constraints unless the user changes them:

- observed data and its provenance;
- mathematical definitions and dimensional consistency;
- explicit experimental conditions;
- required safety, privacy, and access boundaries;
- interfaces that the current experiment genuinely depends on.

Treat these as challengeable soft assumptions unless evidence makes them necessary:

- existing architecture;
- project conventions;
- a preferred library or framework;
- the dominant scientific interpretation;
- imagined future reuse;
- “best practice” that does not affect inference or reproducibility.

Never convert a soft assumption into an unstated requirement.

## 4. Apply the default complexity budget

Unless the task or repository genuinely requires more, use this budget:

- Prefer one executable script or one notebook-equivalent experiment entry point.
- Add at most one raw result artifact and one short result note.
- Prefer editing an existing experiment over creating a new subsystem.
- Add no dependency unless it enables a necessary measurement or prevents a validity error.
- Keep experiment-specific constants visible near the experiment.
- Reuse the repository's existing environment and data path when practical.

Do not add by default:

- abstract base classes, factories, registries, dependency injection, or plugin systems;
- multi-level configuration, generic CLIs, web APIs, GUIs, databases, or services;
- distributed orchestration, caching, concurrency, retries, or checkpoint systems merely for speed or polish;
- compatibility layers, migration frameworks, packaging, deployment files, or release automation;
- broad refactors, style cleanups, or documentation unrelated to the current inference;
- infrastructure for hypothetical future experiments.

A small amount of duplicated or explicit experiment code is preferable to an abstraction that hides the causal path from inputs to observations.

## 5. Require a complexity exception before exceeding the budget

Before adding an extra subsystem, dependency, abstraction, or more than the default file budget, write:

```text
Complexity exception
Blocked scientific inference:
Smallest added component:
Why a simpler alternative fails:
Added files or dependencies:
Condition under which this component can be removed:
```

Proceed only when the added complexity is scientifically necessary or explicitly requested by the user. Convenience, elegance, and possible future reuse are not sufficient.

## 6. Design the smallest discriminating experiment

Prefer an experiment that changes one inferentially important variable at a time.

Include only the controls needed to interpret the result:

- a meaningful baseline or negative control;
- a positive control when failure of the apparatus would otherwise be ambiguous;
- fixed random seeds or an explicit seed set when randomness matters;
- units, dimensions, ranges, and numerical sanity checks;
- data provenance and leakage checks when data are involved;
- raw outputs sufficient to inspect the result;
- the exact command or cell sequence needed to rerun the experiment.

Start with the cheapest sanity run that can reveal an invalid setup. Scale up only when the small run cannot answer the question.

Do not fabricate execution, data, citations, measurements, or successful reproduction. Label simulated evidence as conditional on the simulation model.

## 7. Test scientific correctness, not software completeness

Prioritize checks that can change the inference:

- known limiting cases;
- conservation laws or mathematical invariants;
- unit and dimension consistency;
- baseline equivalence;
- control-group behavior;
- sensitivity to seeds or plausible parameter ranges;
- absence of obvious data leakage;
- agreement with an independently calculable toy case.

Do not build a broad unit-test matrix for getters, serializers, configuration plumbing, or unused extension points unless the user explicitly asks for production engineering.

## 8. Stop when the evidence threshold is reached

Stop implementation as soon as the predefined experiment can support, weaken, falsify, or leave unresolved the target hypothesis.

After reaching the stop condition, do not automatically:

- refactor the experiment into a library;
- add configuration or command-line options;
- optimize performance beyond what the inference needs;
- generate a dashboard or application;
- expand documentation into a product manual;
- continue searching merely to make the project look complete.

Present the result before proposing any next phase.

## 9. Report in epistemic form

Use this result structure:

```text
Status: supports / weakens / falsifies / inconclusive
Observed result:
Comparison with the predeclared decision rule:
Inference justified by the observation:
What is not justified:
Sensitivity and failure modes:
Files changed and the scientific purpose of each:
Engineering deliberately omitted:
Next cheapest discriminating experiment:  # at most one
```

Distinguish explicitly among:

- `[observed]` direct output or supplied fact;
- `[derived]` result following from stated assumptions;
- `[hypothesis]` testable explanation;
- `[speculation]` exploratory possibility.

Do not use implementation completeness, test coverage, code volume, or visual polish as evidence for a scientific claim.

## 10. Audit an overengineered research project

For `AUDIT`, classify each relevant component as:

1. `EPISTEMIC CORE`: directly computes, measures, or distinguishes the hypotheses.
2. `REPRODUCIBILITY SUPPORT`: preserves provenance, environment, raw output, seeds, or exact reruns.
3. `ENGINEERING OVERHEAD`: supports product qualities but not the current inference.
4. `UNKNOWN`: purpose cannot yet be established.

Trace the shortest dependency chain from input data or model assumptions to the reported scientific result. Identify removable components only when their removal does not reduce validity, interpretability, or reproducibility.

Prefer a deletion or simplification plan over a rewrite. Do not replace one framework with another.

For each proposed deletion, state:

```text
Component:
Current role:
Why it is outside the scientific dependency chain:
Risk of removal:
Minimal verification after removal:
```

## 11. Final self-check

Before finishing, answer internally:

- Did I answer a scientific question, or merely produce software?
- Does every new file support inference or reproducibility?
- Did I add an abstraction before observing genuine repetition?
- Did I fix the decision rule before seeing the result?
- Can a reader trace the causal path from assumptions to measurement?
- Have I stopped at the first sufficient result?

If any answer indicates premature engineering, simplify before reporting.

Use `references/output-contract.md` when a more detailed response template is useful. Use `references/audit-checklist.md` for repository simplification tasks.
