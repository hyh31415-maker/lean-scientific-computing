# Verification, Validation, and Calibration Diagnostics

Read this reference when selecting scientific checks or changing scientific behavior, numerics, calibration, outputs, or performance.

Use the fewest checks that can expose a wrong result. Keep three claims separate:

- **Verification:** code implements the declared equations, algorithm, and numerical method.
- **Validation:** model behavior agrees with relevant independent observations.
- **Calibration diagnostics:** parameter estimation is reproducible, interpretable, and sufficiently identifiable for the claim.

One category does not prove another. When a Probe Contract exists, also verify that the implementation preserved its mode-appropriate population, controls, primary observable, rules, and stop condition. DISCOVERY checks must retain branches, failures, and metric changes as exploratory.

## Execution scale and cost

Use the smallest representative dataset and shortest non-empty run that exercise the changed path: a cropped scene, short window, small grid, box case, few optimizer iterations, or reduced ensemble.

Full production data, paid compute, remote scheduling, long optimization, and large ensembles require an explicit current-task request. Never overwrite an existing result for a smoke test.

## Verification

Select only relevant checks.

### Inputs and preprocessing

- Exercise one real or faithful representative input.
- Check relevant variables, shapes/dimensions, coordinates, units, calendars, flags, masks, missingness, and ranges.
- Probe important selection boundaries and one known conversion, aggregation, interpolation, regridding, normalization, or split.
- Confirm authoritative input remains unchanged and confirmatory population/exclusion rules did not drift.

### Equations, processes, and budgets

- Compare a known value with a hand calculation or simpler independent formulation.
- Check relevant dimensions, zero/limit behavior, sign, monotonicity, continuity, or thresholds.
- Check affected mass, elemental, energy, charge, or probability budgets with external terms accounted for.
- Check diagnostic identities such as a net rate equaling its documented component sum.

One or two discriminating cases are preferable to a low-information combinatorial suite.

### Solver and numerics

- Compare with an analytic, quasi-analytic, or simplified case when available.
- Test step size, tolerance, resolution, and convergence only where they could affect the conclusion.
- Surface failure and non-convergence rather than silently converting them into results.
- For stochastic work, record seeds and compare distributions or summaries appropriate to the claim; a fixed-seed regression alone is insufficient.
- Do not tune numerical settings after seeing the desired confirmatory answer. Preserve discovery tuning branches rather than only the favorable run.

### Outputs and provenance

- Reopen the written artifact.
- Check relevant names, dimensions, coordinates, units, missing values, and conventions.
- Confirm diagnostics, configuration, and resolved parameters belong to the same run and outputs do not overwrite inputs.
- Retain raw primary output, controls, failed runs, exploratory branches, and declared contract deviations.

## Validation

Use independent evidence appropriate to the claim, such as held-out time, space, depth, treatment, instrument, or environmental regime. Preserve the observation operator and preprocessing, and report what was held out and which discriminator or metric was used.

A calibration fit is not validation. Verification, internal consistency, visual plausibility, and agreement with training data are not evidence that the model represents nature. When no independent observation exists, state that validation was not performed.

## Calibration diagnostics

Inspect the relevant subset:

- objective components by dataset or variable;
- observation mapping, missing-data treatment, scaling, weights, covariance, or likelihood;
- parameter order, fixed/tunable selection, bounds, transforms, priors, seed, and initialization;
- sensitivity before expensive joint optimization;
- gradient checks when a result depends on gradients;
- alternate starts when consequential local minima are plausible;
- practical identifiability, compensation, and boundary-hitting solutions.

Use ensemble, Bayesian, data-assimilation, or PEST++ machinery only when uncertainty or inverse structure is part of the research requirement. Do not present one optimum as uniquely true without evidence.

## Performance and simplification

For performance work, benchmark a representative measured bottleneck before editing. Report both performance and scientific-result deltas under comparable conditions, with a method-justified tolerance. Inspect affected reduction order, determinism, precision, memory layout, integration trajectory, random streams, and backend consistency.

For behavior-preserving simplification, capture a meaningful output, budget, or objective before editing; compare the same representative case afterward; confirm the contract or declared science did not drift and only the superseded route disappeared.

An import, lint, type check, or generic suite cannot replace either comparison.

## Completion claims

State commands, data scale, and cases actually run. Distinguish inspection, synthetic checks, representative-data smoke tests, calibration diagnostics, validation, and full experiments. A skipped, empty, setup-only, or uninspected output is not a pass. Stop after the requested result and its falsifying checks are complete.
