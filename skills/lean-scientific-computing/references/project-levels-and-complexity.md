# Project Levels and Complexity

Read this reference when the task creates or restructures a project, simplifies an overbuilt repository, or considers a new dependency, directory, abstraction, data store, workflow engine, compatibility layer, or coupling interface.

## Two independent axes

Do not confuse research phase with project maturity.

```text
research phase:   discovery/question -> Probe Contract -> implementation -> Evidence Record -> inference
project maturity: C0 exploration -> C1 reproducible study -> C2 shared component -> C3 operational system
```

`scientific-probe` owns the inquiry mode, scientific target, and Probe Contract. This Skill owns the proportional implementation level. A rigorous discovery or confirmatory probe may use a C0 script, while a settled method may require a C2 component. Neither axis proves the other.

## Project levels

Infer the level from current users and obligations. Do not force a questionnaire or print the classification on every task.

| Level | Current obligation | Proportional structure | Do not add by default |
|---|---|---|---|
| C0 — rapid exploration | Obtain a first discovery, discriminating, or feasibility result | A notebook or a few scripts; a representative input; seed, branch log, and key raw output when relevant | Package layout, generic CLI, test hierarchy, CI, workflow engine |
| C1 — reproducible study | The researcher or a small group must rerun, inspect, compare, and defend the result | One direct run path; explicit inputs, model, parameters, outputs, provenance, and focused science checks | Service layers, database, plugin system, compatibility policy, deployment stack |
| C2 — shared model component | Multiple real projects, researchers, or host models consume the code | Stable boundary, packaging, user documentation, interface tests, and broader regression coverage | Operational infrastructure unrelated to those consumers |
| C3 — operational or externally served system | External users depend on availability, compatibility, security, or published behavior | Normal production engineering, deployment, monitoring, security, migration, and support practices | Artificial minimalism that hides real obligations |

For a new researcher-controlled study, default to C1. Preserve C0 when the user wants a reversible probe or bounded discovery branch. Promote only when a current obligation appears; never promote because reuse is merely imaginable. Discovery mode does not itself justify an experiment-management platform.

## Roles, not a mandatory scaffold

For a new C1 project with no established convention, these roles usually need a home:

```text
run entrypoint
scientific model
parameter source of truth
input catalog or acquisition recipe
calibration driver          # only if calibration exists
focused science checks
generated evidence artifacts
```

They need not be separate files. A small project may use `run.py`, `model.py`, `parameters.yaml`, `data/catalog.yaml`, and `test_science.py`; add `calibrate.py` only when calibration exists. Create `src/`, packages, subpackages, or multiple configuration trees only when existing size or real reuse makes them clearer.

Do not reorganize an existing repository to match this example. A role becomes a separate module when it has an independent reason to change or is obscuring the scientific path—not to satisfy a generic template.

## Promotion ladders

| Surface | Default | Evidence that earns promotion | Promoted option |
|---|---|---|---|
| Input assets | A small YAML/JSON/CSV catalog and explicit loader | Search across many collections or assets is repeated | Intake-ESM or a static STAC catalog |
| Data persistence | NetCDF, Zarr, Parquet, CSV, or provider-owned files | Mutable records, concurrent writes, transactions, or relational queries are current | A database with the narrowest useful schema |
| Remote fixed files | Provider URL plus version or checksum | Repeated automatic downloads and cache validation | Pooch or an equivalent content-addressed cache |
| Experiment execution | One entrypoint and a small experiment table or loop | Repeated DAGs, partial recomputation, scheduler integration, or large HPC ensembles | Snakemake or an existing workflow system |
| Model coupling | Direct call or thin adapter | A second real host or fixed external exchange contract | A minimal BMI/FABM-style boundary |
| Parameter fitting | Explicit objective, bounds/transforms, and local optimizer | High-dimensional inversion, ensemble uncertainty, correlated errors, or assimilation are research requirements | PEST++, ensemble, or Bayesian machinery |
| Output | Self-describing files, compact Evidence Record, and exploration log when applicable | External consumers have a real query, service, or compatibility need | Catalog, API, or product layer scoped to that need |

A mature tool can be safer after the need exists; its maturity does not create the need.

## New structure and dependency test

Before adding a permanent mechanism, establish:

- current requirement or observed failure it owns;
- simpler local alternative considered;
- real consumers or variants, when generic;
- scientific concepts it makes easier to inspect;
- removal path if the assumption proves wrong.

If the justification depends on a hypothetical future story, do not add it.

## Simplifying an overbuilt project

Simplification is behavior-preserving work, not a rewrite.

1. Freeze the Probe Contract, reported result, or representative Evidence Record.
2. Identify authoritative inputs, equations, parameter source, objective, solver entry, diagnostics, and output.
3. Exercise one representative case before changing structure.
4. Mark wrappers, registries, adapters, duplicated configuration, compatibility branches, and orchestration layers with only one live implementation or consumer.
5. Collapse one unnecessary seam at a time into its actual owner.
6. Delete the superseded path in the same change.
7. Re-run the scientific checks and compare meaningful outputs within a justified tolerance.

Prefer fewer decision owners and one readable control path. Do not chase minimum line count: explicit named scientific functions and tables can improve auditability.

## Lightweight simplifier pass

After a non-trivial edit, ask:

- Can a new single-use wrapper or base class disappear?
- Did the change create a second way to run, configure, load, or save the same science?
- Is old code or configuration now superseded?
- Did a future-facing field, flag, dependency, or directory appear without a current consumer?
- Did implementation change any frozen decision rule or scientific population?

Fix only what is directly supported by the task, then stop.
