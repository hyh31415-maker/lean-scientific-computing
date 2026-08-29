---
name: scientific-probe
description: Frame unresolved scientific questions and design or interpret evidence that can change the answer. Use for mechanism discovery, competing hypotheses, effect existence, replication criteria, anomaly diagnosis, causal discrimination, or choosing the next experiment; also for 科学问题、机制、假说、复现、证伪、判别实验. Select DISCOVERY, DISCRIMINATION, or REPLICATION mode, produce a compact Probe Contract, and hand non-trivial computation to lean-scientific-computing. Do not use for already-specified implementation, repository simplification, generic literature summaries, or product delivery.
license: MIT
metadata:
  author: hyh31415-maker
  version: "0.2.0"
  suite: lean-scientific-research
  role: epistemic-design
---

# Scientific Probe

## Mission

Reduce scientific uncertainty without collapsing prematurely onto the safest familiar explanation.

Explore broadly enough to expose consequential alternatives, then constrain claims to the evidence actually produced. Code may serve as experimental apparatus, but software completion is never the scientific result.

A Probe Contract freezes one probe, not the entire research program. New evidence may justify a new branch and a new contract.

## Scope and routing

Use this Skill when the primary unresolved work is epistemic:

- determine whether an effect exists;
- discover or compare mechanisms, explanations, causal stories, or model classes;
- diagnose a surprising observation or disagreement;
- define what would count as replication or failed replication;
- identify a discriminating observation, intervention, statistic, counterexample, or limiting case;
- interpret evidence and choose the next scientific action.

Use `$lean-scientific-computing` when the target computation is already defined and the remaining work is implementation, data preparation, simulation, calibration plumbing, diagnostics, scientific verification, or repository simplification.

For mixed work, use one sequence:

```text
$scientific-probe -> Probe Contract -> $lean-scientific-computing
-> Evidence Record -> $scientific-probe
```

Do not design a product system in parallel with an unresolved probe unless a product constraint materially changes the scientific test. If the sibling Skill is unavailable, preserve the same boundary locally rather than blocking.

## Select the inquiry mode

Choose the mode before designing the probe. State it only when it affects the workflow.

### DISCOVERY

Use when the hypothesis space is incomplete, an observation is surprising, or the purpose is to find a useful mechanism or discriminator.

- Surface consequential hidden assumptions.
- Generate structurally different candidates, not paraphrases.
- Include a non-default explanation when it is mechanistically coherent, not merely contrarian.
- Permit bounded adaptive branches and anomaly-driven iteration.
- Log every branch, changed metric, and selection criterion.
- Report discoveries as exploratory; do not upgrade a selected branch into confirmatory evidence.

### DISCRIMINATION

Use when credible alternatives already exist and make different predictions. Freeze the primary discriminator, analysis rule, decision rule, and stop rule before inspecting the outcome.

### REPLICATION

Use when testing an existing reported result. Freeze the population, exclusions, sample-changing preprocessing, primary statistic, success/failure rule, and stop rule before rerunning it.

Changing mode requires a new Probe Contract. A discovery result may motivate a later discrimination or replication test, but it does not retroactively become one.

## Evidence discipline

- Never invent data, execution, citations, measurements, or successful reproduction.
- Distinguish observed facts from assumptions, derivations, model-dependent results, exploratory findings, and speculation.
- Do not treat reproducing a pattern in a simulation as proof that the simulated mechanism caused the real observation.
- Do not hide failed runs, control failures, exclusions, branches, or contract deviations.
- Treat safety, privacy, data integrity, mathematical definitions, and explicit user constraints as hard constraints.
- Treat prevailing interpretations, existing architecture, preferred libraries, and imagined future reuse as challengeable assumptions.

## Workflow

### 1. Name the scientific target

For DISCRIMINATION or REPLICATION, state the decision or belief that could change.

For DISCOVERY, state the anomaly, unexplained regularity, or search target and what would count as progress: a new predictive mechanism, a localized failure assumption, or a stronger discriminator.

Do not begin with a software deliverable. “Build a pipeline” is not a scientific target.

### 2. Diverge, then compress

Generate the smallest adequate set of materially different candidates, usually two to five. In DISCOVERY, first challenge the most consequential assumptions before selecting leading candidates.

For each candidate, state:

- mechanism or defining assumption;
- prediction under the proposed conditions;
- observation that would weaken it;
- assumptions shared with competitors.

Group candidates that make the same observable prediction under the current probe. Do not force every problem into binary `H0`/`H1`, and do not add novelty that has no distinct testable consequence.

### 3. Find a real discriminator

Prefer an observable on which credible candidates predict different directions, scales, shapes, timings, responses, or budget signatures.

Check:

- expected effect scale versus measurement resolution, sample size, or numerical tolerance;
- controls needed to distinguish a null result from apparatus failure;
- confounders, leakage, or preprocessing choices that can mimic the signal;
- whether the result depends on a simulation model or observation operator;
- whether a simpler counterexample or limiting case settles the issue.

If all candidates predict the same outcome, redesign the probe rather than collecting non-discriminating evidence.

### 4. Choose the minimum sufficient probe

Optimize expected information gain against implementation, compute, data-acquisition, and interpretive cost.

Prefer, when valid:

- a hand calculation or limiting case before a large simulation;
- a synthetic or apparatus control before real-data scale-up;
- a box or 0D model before a spatial host when uncertainty is local;
- one primary statistic before a dashboard of metrics;
- one representative condition plus decisive controls before a broad sweep.

In DISCOVERY, add at most one orthogonal or adversarial probe when it materially protects against a blind spot. A cheap probe is not sufficient if it lacks the power, resolution, or measurement validity needed to change the scientific state.

### 5. Freeze a proportional Probe Contract

Before inspecting the outcome, record the relevant fields:

```text
Mode:
Question, decision, or discovery target:
Current alternatives or search space:
Scope and shared assumptions:
Discriminating prediction or discovery signal:
Probe and controls:
Primary observable or statistic:
Analysis rule:
Decision or branch rule:
Stop rule:
Required raw artifacts and provenance:
Implementation ceiling:
```

Keep this to one screen by default. A simple calculation may need only a few lines. Use [references/probe-contract.md](references/probe-contract.md) for consequential, stochastic, data-dependent, expensive, or multi-stage work.

For DISCRIMINATION and REPLICATION, do not silently revise the population, exclusions, preprocessing, primary statistic, threshold, controls, seed policy, or stop rule after seeing the outcome.

For DISCOVERY, freeze the mechanics and evidence-capture rules of the current probe while allowing logged branches. Post-result choices remain exploratory and need a new contract before confirmatory use.

### 6. Execute or hand off

A trivial scratch calculation may be executed directly.

When the probe requires repository changes, durable data handling, model implementation, calibration, or non-trivial execution, hand the Probe Contract to `$lean-scientific-computing`. That Skill owns structure and scientific verification; this Skill retains ownership of the question, mode, and interpretation.

Set only an implementation ceiling needed to prevent premature productization. Do not prescribe factories, directory layouts, services, or generic interfaces without a scientific requirement.

### 7. Apply the surprise protocol

If a control fails, the measurement cannot resolve the discriminator, or the observation is incompatible with all current candidates:

1. mark the current probe `invalid` or `unresolved`;
2. preserve the unexpected evidence;
3. reopen the smallest assumption set capable of explaining the discrepancy;
4. generate a new exploratory contract.

Do not patch the old threshold, metric, model, or sample until it appears successful.

### 8. Interpret the Evidence Record

Compare the result with the mode-appropriate rule.

For DISCRIMINATION or REPLICATION, report:

```text
Status: supports / weakens / incompatible under assumptions / unresolved / invalid probe
```

For DISCOVERY, report:

```text
Status: candidate generated / anomaly localized / discriminator improved / unresolved / invalid probe
```

Use evidence labels:

```text
[observed] Direct outputs or supplied facts
[derived] Consequences following from stated assumptions
[model-dependent] Conclusions conditional on a model or observation operator
[exploratory] Findings selected or changed after outcome inspection
[speculation] Plausible but currently untested ideas
```

State contract deviations and what the evidence does not establish. “Supports” means a relative belief update, not proof.

### 9. Stop deliberately

Stop when the declared decision is possible, the discovery target has advanced enough to define the next probe, or the current probe is shown invalid.

Do not continue with unsolicited refactoring, packaging, optimization, dashboards, APIs, broad parameter sweeps, or literature expansion. Name at most one next probe unless the user explicitly requests a research program.

## Failure modes and completion

Read [references/failure-modes.md](references/failure-modes.md) for ambiguous hypotheses, premature formalization, post-result analysis, simulation-to-reality claims, leakage, or repeated metric changes.

Before finishing, verify:

- the selected mode matches the epistemic state;
- the candidates are materially distinct and testable;
- the observable can discriminate or discover something useful;
- confirmatory rules predate the outcome;
- exploratory branches remain visibly exploratory;
- evidence labels match what actually occurred;
- no engineering milestone is being used as scientific evidence;
- the work stopped at the first sufficient result.

Read files under `evals/` only when revising or evaluating this Skill.
