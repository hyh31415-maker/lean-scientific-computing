# Scientific Spine

Read this reference when changing scientific inputs, preprocessing, equations, parameters, objectives, calibration, provenance, diagnostics, or outputs.

The scientific spine is the shortest inspectable chain from source data and assumptions to evidence:

```text
input identity -> preprocessing -> state/forcing -> process model -> numerics
                                        ^                 |
                              resolved parameters          v
observations -----------------------> objective <- diagnostics/output
                                                          |
                                                          v
                                                   Evidence Record
```

Give each scientific semantic one authoritative resolution chain, not necessarily one file. Base definitions, experiment overrides, and resolved run snapshots are legitimate layers when one resolver makes precedence visible. Avoid competing truths in loaders, model objects, notebooks, optimizer arrays, and reporting code.

When a Probe Contract exists, preserve its population, preprocessing, controls, primary observable, analysis or branch rule, and required raw artifacts along this spine.

## Inputs and preprocessing

Keep authoritative inputs unchanged when practical. For remote or large data, record an exact acquisition recipe rather than treating a transient local copy as authoritative.

A small catalog needs only study-relevant identity: logical name, provider location, product/version, consumed variables and units, domain/time selection when not configured elsewhere, acquisition/preprocessing owner, stable revision or checksum, and reuse constraints. Do not duplicate authoritative metadata or store credentials.

Separate transformations from raw inputs. Expose applicable choices: variables and coordinates; masks, flags, quality filtering, missingness, and detection limits; units and normalization; temporal aggregation/interpolation; reprojection, regridding, vertical conventions; and calibration/validation or train/test partitions.

Avoid silent repair and broad fallback. A fallback that changes the scientific sample is more dangerous than a clear failure. Keep changed discovery branches visible; amend a confirmatory contract before using a sample-changing branch as confirmatory evidence.

## Scientific core and parameters

Keep state, forcing, observations, parameters, process rates, tendencies, constraints, and diagnostics distinguishable. A reader should be able to trace each state change to its equation, parameters and units, numerical treatment, and inspectable intermediate quantities.

Prefer pure or nearly pure process functions when compatible with the repository. Do not hide equations behind generic factories, registries, or serialization solely for configurability.

Use only the parameter layers the study needs:

```text
parameter definition -> experiment override -> resolved run snapshot
```

- **Definition:** semantics, units, reference/default value, bounds, transform, tunability, owner, source, and rationale as applicable.
- **Override:** experiment-specific values without redefining semantics.
- **Snapshot:** fully resolved values used for the result.

Generate optimizer vectors and display tables from this chain. Do not copy defaults or bounds independently across code, configuration, arrays, and notebooks. Priors and literature values must come from the task, repository, or a verified source.

## Result-specific paths and calibration

Simulation, calibration, sensitivity, validation, and product generation are distinct results. Keep a thin authoritative entrypoint and configuration-resolution path for each result that exists. Share loaders, equations, parameter semantics, and output writers when they represent the same science; avoid both duplicated cores and one switch-heavy universal driver.

Keep process equations independent from the optimizer unless a tested project convention requires otherwise. Make applicable observation data and preprocessing, observation operator, residual or likelihood, scaling/weights/covariance, detection-limit treatment, parameter transforms/bounds, fixed/tunable selection, seed, initialization, and held-out regimes inspectable. Expose objective components by dataset or variable.

## Diagnostics, outputs, and handoff

Preserve variable identity, units, dimensions, coordinates, and missing-value semantics. Export diagnostics from their scientific owner instead of reimplementing equations downstream.

For a substantive run, record the relevant code revision, input identity, experiment configuration, resolved parameters, objective, seed, numerics, output location/metadata, budget or residual summaries, run classification, failed runs, and contract deviations. Output attributes or a compact manifest are usually sufficient; do not build a tracking service without a current requirement.

The Evidence Record is an audit aid, not automatically a project artifact. Keep it in the response unless durable output is requested, and include only what is needed to rerun or interpret the result.
