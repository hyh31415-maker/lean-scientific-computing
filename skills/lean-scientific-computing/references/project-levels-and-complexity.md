# Project Levels and Complexity

Read this reference when the task creates or restructures a project, simplifies an overbuilt repository, or considers a new dependency, directory, abstraction, data store, workflow engine, compatibility layer, or coupling interface.

## Project levels

Infer the level from current users and obligations. Do not force a questionnaire or print the classification on every task.

| Level | Current obligation | Proportional structure | Do not add by default |
|---|---|---|---|
| C0 — rapid exploration | Decide whether an idea, mechanism, or method deserves more work | A notebook or a few scripts; a representative input; seed and key output when relevant | Package layout, CLI, test hierarchy, CI, workflow engine |
| C1 — reproducible study | The researcher or a small group must rerun, inspect, compare, and defend the result | One direct run path; explicit inputs, model, parameters, and outputs; focused science checks | Service layers, database, plugin system, compatibility policy, deployment stack |
| C2 — shared model component | Multiple real projects, researchers, or host models consume the code | Stable boundary, packaging, user documentation, interface tests, broader regression coverage | Operational infrastructure unrelated to those consumers |
| C3 — operational or externally served system | External users depend on availability, compatibility, security, or published behavior | Normal production engineering, deployment, monitoring, security, migration, and support practices | Artificial minimalism that hides real operational obligations |

For a new researcher-controlled study, default to C1. Preserve C0 when the user wants a quick exploration. Promote only when a current obligation appears; never promote because reuse is merely imaginable.

## Roles, not a mandatory scaffold

For a new C1 project with no established convention, these roles usually need a home:

```text
run entrypoint
scientific model
parameter source of truth
input catalog or acquisition recipe
calibration driver          # only if calibration exists
focused science checks
generated results
```

They need not be separate files. A small project may use `run.py`, `model.py`, `parameters.yaml`, `data/catalog.yaml`, and `test_science.py`; add `calibrate.py` only when calibration exists. Create `src/`, packages, subpackages, or multiple configuration trees only when the existing size or reuse makes them clearer.

Do not reorganize an existing repository to match this example. A role should become a separate module when it has an independent reason to change or is already obscuring the scientific path—not to satisfy a generic template.

## Promotion ladders

| Surface | Default | Evidence that earns promotion | Promoted option |
|---|---|---|---|
| Input assets | A small YAML/JSON/CSV catalog and explicit loader | Search across many collections or assets is a repeated task | Intake-ESM or a static STAC catalog |
| Data persistence | NetCDF, Zarr, Parquet, CSV, or files owned by the provider | Mutable records, concurrent writes, transactional updates, or complex relational queries are current requirements | A database with the narrowest useful schema |
| Remote fixed files | Provider URL plus version or checksum | Repeated automatic downloads and cache validation | Pooch or an equivalent content-addressed cache |
| Experiment execution | One run entrypoint and a small experiment table or loop | Repeated multi-stage DAGs, partial recomputation, scheduler integration, or large HPC ensembles | Snakemake or an existing workflow system |
| Model coupling | Direct call or thin adapter | A second real host or a fixed external exchange contract | A minimal BMI/FABM-style boundary |
| Parameter fitting | Explicit objective, bounds/transforms, and a local optimizer | High-dimensional environmental inversion, ensemble uncertainty, correlated errors, or data assimilation are research requirements | PEST++, ensemble, or Bayesian machinery |
| Output | Self-describing files and a compact run record | External consumers have a real query, service, or compatibility need | Catalog, API, or product layer scoped to that need |

Do not introduce a promoted option merely because it is mature or popular. Maturity makes a tool safer after the need exists; it does not create the need.

## New structure and dependency test

Before adding a permanent mechanism, record the decision mentally or in one concise implementation note:

- current requirement or observed failure it owns;
- simpler local alternative considered;
- real consumers or variants, when generic;
- scientific concepts it makes easier to inspect;
- removal path if the assumption proves wrong.

If the justification needs a hypothetical future story, do not add it.

## Simplifying an overbuilt project

Simplification is behavior-preserving work, not a rewrite.

1. Freeze the current scientific route: authoritative inputs, equations, parameter source, objective, solver entry, diagnostics, and representative outputs.
2. Exercise one representative case before changing structure.
3. Mark wrappers, registries, adapters, duplicated configuration, compatibility branches, and orchestration layers that have only one live implementation or consumer.
4. Collapse one unnecessary seam at a time into its actual owner.
5. Delete the superseded path in the same change; do not leave old and new routes side by side.
6. Re-run the scientific checks that protect meaning, not only import or style checks.

Prefer fewer decision owners and one readable control path. Do not chase minimum line count: a named process function or explicit table is valuable when it exposes scientific meaning.

## Lightweight simplifier pass

After a non-trivial edit, ask:

- Can any new single-use wrapper or base class disappear?
- Did the change create a second way to run, configure, load, or save the same science?
- Is any old code or configuration now superseded?
- Did a future-facing field, flag, dependency, or directory slip in without a current consumer?

Fix what is directly supported by the current task, then stop. Reserve independent audit or multi-role workflows for large, risky, or explicitly reviewed changes.
