# Scientific Spine

Read this reference when changing scientific inputs, preprocessing, equations, parameters, objectives, calibration, provenance, diagnostics, or outputs.

The scientific spine is the shortest inspectable chain from source data and assumptions to a result:

```text
input catalog -> preprocessing -> state/forcing -> process model -> solver
                                      ^                 |
                                  parameters            v
observations --------------------> objective <- diagnostics/output
```

Keep one authoritative surface for each role. Do not duplicate scientific truth across loaders, configuration layers, model objects, notebooks, and reporting code.

## Inputs and acquisition

Keep authoritative or raw inputs unchanged when practical. If a stable remote database is too large to copy, record an exact acquisition recipe rather than pretending a local copy is the source of truth.

A lightweight input catalog may be a small table or mapping with only fields that matter to reproducibility:

| Field | Purpose |
|---|---|
| `name` | Stable logical identifier used by the project |
| `uri` or `path` | Provider location or project-relative location |
| `product` and `version` | Dataset identity |
| `variables` | Variables actually consumed |
| `units` | Expected source units or unit mapping |
| `spatial_extent` / `time_extent` | Selected domain, if not obvious from configuration |
| `acquire` | Script, query, or documented retrieval method |
| `preprocess` | Owning transformation entrypoint |
| `checksum` or provider revision | Stable identity when available |
| `source` / `license` | Provenance and reuse constraints |

Do not require every field when the information is already authoritative and unambiguous elsewhere. Do not store credentials, cookies, or tokens in the catalog.

## Preprocessing

Make destructive-looking transformations reproducible and separate from raw inputs. A preprocessing path should make these choices visible when relevant:

- variable and coordinate selection;
- masks, flags, quality filters, and missing-value handling;
- unit conversion;
- temporal aggregation or interpolation;
- spatial reprojection, regridding, or vertical interpolation;
- normalization, detection limits, or below-quantification treatment;
- train/calibration/validation partitioning.

Avoid silent repair and broad fallback behavior. A permissive fallback that changes the scientific sample is more dangerous than a clear failure.

## Scientific core

Keep state, forcing, parameters, process rates, tendencies, constraints, and diagnostics explicit. A reader should be able to answer:

- Which variables are prognostic state, diagnostic state, forcing, or observations?
- Which equation or process changes each state variable?
- Which parameters control the process and in what units?
- Which terms are externally transported or numerically integrated?
- Which intermediate quantities can be inspected after a run?

Prefer pure or nearly pure process functions when the language and existing project allow it. Do not hide equations behind generic factories, callback registries, or serialization machinery solely to make them configurable.

## Parameter source of truth

Use one authoritative registry in code or configuration. Useful fields include:

```text
name, symbol, units, default, bounds, transform, tunable,
process, source, rationale, prior
```

Include only fields the study uses. `source` identifies evidence or inheritance; `rationale` explains the current modeling choice. Treat a working value as provisional without repeating caveats throughout the project.

Do not maintain separate defaults in a class, YAML file, optimizer bounds array, and notebook. Generate optimizer vectors or display tables from the authoritative registry when needed.

## Objective and calibration

Keep the model equations independent from the optimizer unless the existing framework has a clear, tested convention otherwise. Make the following inspectable:

- observation datasets and preprocessing;
- simulated quantity matched to each observation;
- residual or likelihood definition;
- scaling, weighting, covariance, or detection-limit treatment;
- parameter transforms and bounds;
- fixed versus tunable parameters;
- random seed and initialization or multi-start policy;
- calibration and held-out regimes.

An objective function should expose interpretable components. A single opaque score makes scientific trade-offs and dataset dominance hard to audit.

## Diagnostics and outputs

Save outputs in a form that preserves variable identity, units, dimensions, coordinates, and relevant missing-value semantics. Prefer diagnostics already computed by the scientific core over reimplementing process equations in plotting or reporting code.

For a substantive C1 run, record the relevant subset of:

- code revision and whether the tree was dirty;
- input catalog identity, provider revision, or checksums;
- experiment configuration and parameter snapshot;
- objective definition and observation set;
- random seed;
- solver and tolerances when they affect results;
- output location and variable metadata;
- scientific budget or residual summaries.

Do not build an experiment-tracking service to store this record. A compact machine-readable run manifest or attributes in the output file are normally sufficient.

## Science diff for handoff

Report only touched surfaces:

- input or preprocessing selection;
- equations, rates, constraints, or conservation behavior;
- parameters, bounds, transforms, priors, or objective;
- calibration or solver behavior;
- diagnostics, metadata, or output;
- infrastructure added and the current requirement that earned it;
- checks actually run.

This science diff is an audit aid, not a new project artifact unless the user asks to retain it.
