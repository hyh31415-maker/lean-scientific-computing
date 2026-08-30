# Project Levels and Complexity

Read this reference when creating or restructuring a project, simplifying an overbuilt repository, or considering a permanent dependency, directory, abstraction, data store, workflow system, compatibility layer, or coupling interface.

## Keep two axes separate

```text
research phase:   discovery -> Probe Contract -> implementation -> Evidence Record -> inference
project maturity: C0 exploration -> C1 reproducible study -> C2 shared component -> C3 operational system
```

A rigorous discovery or confirmatory probe may use a C0 script. A settled method may need a C2 component. Evidence strength and software maturity do not prove one another.

## Choose the lowest adequate level

Infer the level from current obligations, not repository age or imagined reuse. Do not ask for or print a classification unless it changes the work.

| Level | Current obligation | Proportional structure | Do not add by default |
|---|---|---|---|
| C0 — exploration | Decide whether an idea, mechanism, or method deserves more work | Notebook or a few scripts, representative input, key assumptions, seed and branch log when relevant, inspectable output | Package layout, CLI, test hierarchy, CI, workflow engine |
| C1 — reproducible study | Rerun, compare, cite, share within a small group, or defend a result | Authoritative paths per result, explicit input/equation/parameter resolution, focused science checks, compact provenance | Service layers, database, plugin system, compatibility policy, deployment stack |
| C2 — shared component | Multiple real projects, researchers, or hosts consume the code | Stable narrow boundary, packaging, user documentation, interface tests, broader regression coverage | Operational machinery unrelated to those consumers |
| C3 — operational system | External users depend on availability, security, compatibility, or published behavior | Normal production engineering, deployment, monitoring, migration, and support | Minimalism that hides operational obligations |

An explicit prototype is normally C0. Use C1 when the result must be rerun, compared, cited, shared, or defended. A new project alone does not earn C1. Promote only when a present obligation appears.

## Roles are not a scaffold

A C1 study normally makes these responsibilities findable:

```text
result entrypoint(s)
scientific model and parameter-resolution chain
input acquisition and preprocessing
calibration or inference driver, only when used
focused scientific checks
outputs and compact run provenance
```

Do not turn this list into one directory or file per role. A notebook or two scripts may own several responsibilities clearly. Split only when a responsibility has an independent reason to change or the scientific route is already obscured. Preserve the repository's established layout.

Different results may use separate thin entrypoints. They should call the same scientific core and parameter resolver rather than merge into a switch-heavy universal driver or duplicate equations.

## Promotion ladders

| Surface | Local default | Evidence that earns promotion | Promoted option |
|---|---|---|---|
| Input assets | Small mapping/table and explicit loader | Repeated discovery across many collections | Intake-ESM or static STAC catalog |
| Persistence | Provider-owned or self-describing files | Mutable records, concurrent writes, transactions, or relational queries | Narrow database schema |
| Remote files | Provider URL plus version/checksum | Repeated downloads and cache validation | Pooch or equivalent cache |
| Execution | Thin result entrypoint and small experiment table/loop | Repeated DAGs, partial recomputation, scheduler integration, or large ensembles | Existing workflow system |
| Coupling | Direct call or thin adapter | Second real host or fixed exchange contract | Minimal BMI/FABM-style boundary |
| Fitting | Explicit objective, bounds/transforms, seed, local optimizer | High-dimensional inversion, ensemble uncertainty, correlated errors, or assimilation is part of the research | PEST++, ensemble, or Bayesian machinery |
| Output | Self-describing files and compact Evidence Record | External consumers have a real query, service, or compatibility need | Scoped catalog, API, or product layer |

A tool's maturity or popularity is not an activation condition.

## Simplifying an overbuilt project

1. Freeze the relevant Probe Contract or scientific route: inputs, equations, parameter resolution, objective, solver entry, diagnostics, and representative outputs.
2. Run the smallest representative case before structural edits.
3. Within the requested surface, find wrappers, registries, adapters, duplicate configuration, or orchestration with one live implementation or consumer.
4. Collapse one unnecessary seam into its owner and delete only the path made unused by that collapse.
5. Compare the protected result within a justified tolerance and run the final authoritative entrypoint.

Prefer fewer decision owners, not merely fewer lines. After a non-trivial edit, inspect only the changed surface for a new single-use wrapper, duplicate control path, superseded file, or future-facing flag. Fix what this change introduced, then stop.
