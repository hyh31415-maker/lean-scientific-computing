# Behavioral Evaluation Protocol

Read this file only when creating, revising, or evaluating `lean-scientific-computing`. Evaluate observable routing, decisions, diffs, commands, artifacts, and Evidence Records—not wording or heading similarity.

## Current evidence status

This is an evaluation specification, not a claim that behavioral comparisons have passed. Do not call the Skill validated until reproducible run records and artifacts exist.

## Make each case executable

Freeze before running:

- fixture repository and exact commit or content hash;
- user prompt, starting files, allowed paths, and protected paths;
- Skill commit and comparison condition;
- model, reasoning setting, host version, and tool permissions;
- permitted commands and execution-cost limits;
- scientific invariant, Probe Contract when present, and observable architecture boundary.

Run each condition from an identical isolated copy. Preserve transcript, final status, diff, commands and outputs, result artifacts, and reviewer decision. A prose recollection is not a run record.

Useful comparison conditions are:

1. the same prompt with this Skill disabled;
2. the same ordinary prompt with implicit selection enabled;
3. explicit `$lean-scientific-computing` invocation or the previous Skill revision.

Keep model, reasoning, fixture, permissions, and prompt constant. Otherwise label the comparison exploratory.

## Measures

Record at least:

- modified, added, deleted, and protected files;
- lines changed, top-level directories, dependencies, abstractions, configuration owners, and entrypoints added or removed;
- whether a non-empty representative scientific path ran;
- scientific result delta, numerical tolerance, and performance delta when applicable;
- verification, validation, calibration, and interpretation claims;
- contract deviations, exploratory branches, failed runs, silent assumptions, unrequested expensive execution, and unfinished control paths.

Machine diff measures identify review targets; they are not quality scores. Do not reward fewer lines when clarity or a real obligation requires structure. Add a deterministic checker only after a repeated failure can be expressed reliably.

## Global pass conditions

- selects this Skill only when the scientific target is sufficiently defined;
- consumes a `scientific-probe` Probe Contract without restarting inquiry design;
- applies confirmatory locks differently from logged DISCOVERY branches;
- stays on the named scientific surface and preserves unrelated project structure;
- leaves one authoritative execution and configuration-resolution path per distinct result;
- gives every permanent mechanism a current requirement;
- keeps inputs, formulas, parameter resolution, objectives, numerics, diagnostics, and outputs traceable;
- uses representative, non-empty scientific checks and preserves raw outputs, failures, branches, and deviations;
- distinguishes verification, validation, calibration diagnostics, and scientific interpretation;
- stops without adjacent redesign, productization, or a speculative backlog.

Hard failures include:

- silently changing a frozen confirmatory population, preprocessing rule, control, statistic, threshold, or stop rule;
- reporting a selected discovery branch as confirmatory evidence;
- an unearned database, service, plugin system, registry, workflow engine, or compatibility layer;
- duplicate scientific definitions or competing parameter/configuration resolution;
- changed science protected only by import, lint, type, or generic tests;
- silent data repair, sample-changing fallback, scientific choice, or invented evidence or literature value;
- full production data, paid compute, remote scheduling, long optimization, or large ensemble without current-task authorization;
- calling calibration fit or internal consistency validation;
- leaving old and new routes active after simplification or deleting unrelated pre-existing structure;
- suppressing earned C2/C3 engineering despite real external obligations.

## Selection and handoff tests

Implicit invocation is enabled. Positive cases should activate from an ordinary matching prompt; explicit invocation must also work. Negative cases must not activate it.

Positive prompts:

```text
Implement this specified rate equation in the research model and check its carbon budget.
Simplify this scientific repository while preserving the reported numerical result.
Run this frozen comparison and retain its controls and raw outputs.
Build the smallest reproducible parameter inversion from this defined objective.
```

Negative or alternate-owner prompts:

```text
What non-obvious mechanisms could explain this anomaly?          # exploratory-science when installed
Review this pull request.                                        # review workflow
Plot a temperature-salinity profile.                             # visualization workflow
Diagnose this segmentation fault.                               # debugging workflow
Organize my worktrees and research files.                        # workspace workflow
Deploy this validated forecast as an authenticated public API.   # production engineering
```

Mixed work must produce one sequence—Probe Contract, one implementation pass, one Evidence Record, then interpretation—not two independent plans or a handoff loop.

## Contract regression cases

### Confirmatory handoff

Implement a frozen comparison with a specified population, seed set, primary statistic, controls, threshold, and stop rule. Preserve every field, use a direct driver, retain raw results, and do not tune the rule after observing the outcome.

### Discovery handoff

Implement a bounded exploratory probe with specified candidates and one allowed orthogonal branch. Retain every branch, failed run, metric change, and selection criterion; classify the record exploratory; do not construct an experiment platform.

### Unresolved mechanism

For “determine whether this oscillation is physical or numerical and implement what is needed,” route inquiry design to `$scientific-probe` before substantial repository work and consume the resulting contract without duplicate planning.

## Cross-domain behavior matrix

Each row becomes runnable only after fixture, commit, protected paths, and invariant are frozen.

| ID | Scientific task | Discriminating behavior |
|---|---|---|
| C0-NB | Prototype a supplied reaction or oscillation equation | Keep C0; explicit states, parameters, result, one discriminating run; no package, CLI, CI, or scaffold |
| PDE-FD | Change a boundary condition in a finite-difference solver | Edit the owning boundary/numerical surface; use a known or convergence case; no solver-framework rewrite |
| MC-RNG | Vectorize a Monte Carlo estimator | Benchmark first; preserve or document RNG semantics; compare distribution/result and speed |
| INV-STAT | Fit parameters to several observation types | Decomposable objective, transforms/bounds/seeds, sensitivity and compensation checks; no MLOps platform or unique-optimum claim |
| IMG-SPEC | Add a mask or radiometric transform | Preserve product identity, units, axes, masks, and a known pixel or spectrum check |
| ML-SCI | Add one feature or model to a study | Preserve preprocessing and held-out partitions; check leakage; do not equate fit with validation |
| LAB-DATA | Process experimental data with replicates and detection limits | Preserve raw input; expose units, censoring, replicate handling, and treatment groups; no database or dashboard |
| BGC-RATE | Implement a specified Q10 or remineralization form | Edit the owning rate and parameter chain; check reference/warm points and a budget or box result; no plugin system |
| EO-INPUT | Add one satellite product | Thin catalog/adapter, version, flags, units, grid, observation operator, and representative sample; no STAC API or ingestion service |
| SCI-AMB | Two plausible scientific forms change the conclusion | Do not silently choose; encode cheap alternatives or report the branch-level conflict |
| PERF-NUM | Optimize a numerical kernel | Representative before/after benchmark, scientific tolerance, and affected determinism/precision/backend checks |
| SIMPLIFY | Collapse factories and duplicate config around one result | Freeze the result; keep authoritative resolution; delete only superseded paths |
| C2-HOST | Reuse one core in a second real host | Permit a minimal exchange boundary; keep shared equations; avoid unrelated coupling machinery |
| HPC-ENS | Run a large ensemble with scheduler and restart requirements | Permit earned workflow support; retain a direct scientific command and experiment identity |
| C3-API | Serve a validated model with security and compatibility obligations | Route to normal production engineering while preserving the scientific core boundary |
| NO-CODE | Investigate mechanisms or literature without a defined computation | Do not force implementation, project structure, or this Skill's completion format |

## Regression decision

Before claiming a broad improvement, test at least one discovery handoff, confirmatory handoff, C0, C1, C2, C3/out-of-scope, and non-BGC case. A targeted revision may rerun the observed failure plus one nearby counterexample.

Accept a revision only when the observed failure decreases without increasing scope, ceremony, silent scientific choice, false routing, or false claims elsewhere. Record date, Skill and fixture commits, model and reasoning setting, comparison condition, rationale, and artifact location. Without an inspectable run record, report the evaluation as not run.
