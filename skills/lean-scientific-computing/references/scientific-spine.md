# Scientific Spine

Read this reference when changing scientific inputs, preprocessing, equations, parameters, objectives, calibration, provenance, diagnostics, or outputs.

The scientific spine is the shortest inspectable chain from source data and assumptions to evidence:

```text
input catalog -> preprocessing -> state/forcing -> process model -> solver
                                      ^                 |
                                  parameters            v
observations --------------------> objective <- diagnostics/output
                                                        |
                                                        v
                                                Evidence Record
```

Keep one authoritative surface for each role. Do not duplicate scientific truth across loaders, configuration layers, model objects, notebooks, and reporting code.

When a `scientific-probe` Probe Contract exists, the spine must preserve its sample definition, controls, primary observable, analysis rule, and required raw artifacts.

## Inputs and acquisition

Keep authoritative or raw inputs unchanged when practical. If a stable remote database is too large to copy, record an exact acquisition recipe rather than pretending a local copy is the source of truth.

A lightweight input catalog may be a small table or mapping with the relevant subset of:

| Field | Purpose |
|---|---|
| `name` | Stable logical identifier used by the project |
| `uri` or `path` | Provider location or project-relative location |
| `product` and `version` | Dataset identity |
| `variables` | Variables actually consumed |
| `units` | Expected source units or unit mapping |
| `spatial_extent` / `time_extent` | Selected domain |
| `acquire` | Script, query, or retrieval method |
| `preprocess` | Owning transformation entrypoint |
| `checksum` or provider revision | Stable identity when available |
| `source` / `license` | Provenance and reuse constraints |

Do not require redundant fields. Do not store credentials, cookies, or tokens in the catalog.

## Preprocessing

Make sample-changing transformations reproducible and separate from raw inputs:

- variable and coordinate selection;
- masks, flags, quality filters, and missing-value handling;
- unit conversion;
- temporal aggregation or interpolation;
- spatial reprojection, regridding, or vertical interpolation;
- normalization, detection-limit treatment, or censoring;
- calibration, train, validation, or comparison partitioning.

Avoid silent repair and broad fallbacks. A fallback that changes the scientific population is more dangerous than a clear failure. A frozen DISCRIMINATION or REPLICATION contract must be amended explicitly before such a change is used as confirmatory evidence. In DISCOVERY, retain the original and changed branches in the exploration log.

## Scientific core

Keep state, forcing, parameters, process rates, tendencies, constraints, and diagnostics explicit. A reader should be able to answer:

- Which variables are prognostic state, diagnostic state, forcing, or observations?
- Which equation or process changes each state variable?
- Which parameters control the process and in what units?
- Which terms are transported, imposed, or numerically integrated?
- Which intermediate quantities can be inspected after a run?

Prefer pure or nearly pure process functions when compatible with the project. Do not hide equations behind generic factories, callback registries, or serialization machinery merely to make them configurable.

## Parameter source of truth

Use one authoritative registry in code or configuration. Include only fields the study uses, such as:

```text
name, symbol, units, default, bounds, transform, tunable,
process, source, rationale, prior
```

Do not maintain separate defaults in a class, YAML file, optimizer array, and notebook. Generate derived vectors or display tables from the authoritative registry.

## Objective and calibration

Keep model equations independent from the optimizer unless an existing tested convention requires otherwise. Make these inspectable:

- observation datasets and preprocessing;
- simulated quantity matched to each observation;
- residual, likelihood, or comparison statistic;
- scaling, weighting, covariance, and detection-limit treatment;
- parameter transforms and bounds;
- fixed versus tunable parameters;
- seed, initialization, or multi-start policy;
- calibration and held-out regimes.

An objective should expose interpretable components. A single opaque score hides trade-offs and dataset dominance. Do not change a confirmatory primary objective after inspecting the result without labeling the change exploratory. In DISCOVERY, keep every objective or anomaly-score branch and its selection rule.

## Diagnostics and outputs

Save outputs with variable identity, units, dimensions, coordinates, and missing-value semantics. Prefer diagnostics computed by the scientific core over reimplementing equations in plotting or reporting code.

For a substantive run, record the relevant subset of:

- code revision and dirty-tree status;
- input identity, provider revision, or checksums;
- experiment configuration and parameter snapshot;
- objective or comparison definition;
- random seed;
- solver and tolerances;
- raw output location and metadata;
- scientific budgets, residuals, controls, and failures;
- run classification and deviations from the Probe Contract;
- complete exploratory branch and failed-run records when applicable.

A compact machine-readable manifest or output attributes are normally enough. Do not build an experiment-tracking service without a current requirement.

## Evidence Record handoff

Report only facts needed for inference or reproducibility:

- inquiry mode, run classification, and scientific target;
- contract or implementation brief preserved;
- declared deviations;
- exact command or cell sequence;
- input and preprocessing identity;
- parameters, seed, solver, and tolerances when consequential;
- raw artifact and exploration-log locations;
- observed primary statistic, controls, diagnostics, budgets, and failures;
- scientific checks actually run;
- files changed and the scientific role of each.

The Evidence Record is an audit aid, not automatically a new project artifact. It should be sufficient for `scientific-probe` to compare the result with the frozen decision rule without reconstructing implementation history.
