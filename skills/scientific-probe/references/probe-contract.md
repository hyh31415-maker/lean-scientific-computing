# Probe Contract

Use this expanded form only when a probe is consequential, stochastic, data-dependent, expensive, multi-stage, or vulnerable to post-result flexibility. The default contract should fit on one screen.

A contract freezes one probe. It does not freeze the entire research program.

## 1. Mode and target

- Mode: `DISCOVERY`, `DISCRIMINATION`, or `REPLICATION`
- Scientific question, decision, anomaly, or discovery target
- Belief or action that could change
- Scope: population, regime, geometry, timescale, or model class
- What is explicitly out of scope

For DISCOVERY, progress may mean producing a predictive candidate, localizing a broken assumption, or improving the next discriminator. Do not invent a binary threshold merely to make exploration look formal.

## 2. Alternatives or search space

For each current candidate:

- defining mechanism or assumption;
- predicted observable under planned conditions;
- observation that would weaken it;
- assumptions shared with other candidates.

In DISCOVERY, also record the consequential assumptions being challenged and the rule used to select branches. Include a non-default candidate only when it has a coherent mechanism and distinct consequence.

Group observationally equivalent alternatives. Do not claim that a probe separates candidates that make the same prediction.

## 3. Discriminator or discovery signal

- intervention, contrast, limiting case, counterexample, or observation;
- primary observable or statistic;
- expected direction, scale, shape, timing, or budget signature;
- measurement resolution, numerical tolerance, or sample size needed to matter;
- negative control;
- positive or apparatus control when a null result would otherwise be ambiguous;
- known confounders and how they are bounded;
- one optional orthogonal or adversarial probe for DISCOVERY, with its added information value.

## 4. Analysis and branch lock

Record before inspecting the current probe outcome:

- sample inclusion and exclusion rules;
- sample-changing preprocessing;
- observation operator or mapping from model state to measurement;
- statistic, loss, or anomaly score;
- uncertainty interval, tolerance, or decision threshold when applicable;
- seed or initialization policy;
- handling of failed runs and missing observations;
- decision, branch, and stop rules.

Mode-specific discipline:

- **DISCRIMINATION / REPLICATION:** primary analysis and decision rule are frozen. Post-result changes are exploratory.
- **DISCOVERY:** the current probe mechanics and evidence capture are frozen, but adaptive branches are allowed. Log all branches, changed metrics, failed attempts, and selection criteria. A selected result remains exploratory until retested under a new confirmatory contract.

A conventional threshold is not a universal scientific truth. The rule must be explicit and appropriate to the decision.

## 5. Implementation handoff

Specify only what implementation must preserve:

- required inputs and provenance;
- required raw outputs and failed-run records;
- exact comparisons and controls;
- scientific invariants or sanity checks;
- compute or file ceiling;
- conditions that justify exceeding the ceiling.

Do not prescribe factories, services, directory layouts, or generic interfaces. Those decisions belong to `$lean-scientific-computing`.

## 6. Evidence return

The Evidence Record should include:

- run classification: confirmatory, exploratory, feasibility-only, or invalid;
- exact command or cell sequence;
- code revision and relevant environment;
- input identity and preprocessing;
- seed or initialization;
- raw artifact locations;
- observed primary statistic, controls, and branch log when applicable;
- scientific checks actually run;
- failed runs and contract deviations.

## 7. Interpretation

Compare the Evidence Record with the mode-appropriate rule. Label conclusions as observed, derived, model-dependent, exploratory, or speculative. State what the probe cannot establish.

If controls fail or all candidates miss the observation, preserve the surprise, mark the current probe invalid or unresolved, and create a new exploratory contract. Do not repair the old rule after the result.
