# Scientific Verification

Read this reference when selecting checks, modifying scientific behavior, or changing calibration, optimization, or outputs.

Verification is proportional to the scientific consequence. The goal is to expose a wrong result with the fewest meaningful checks, not to maximize test count or coverage.

## Verification by project level

| Level | Minimum useful evidence |
|---|---|
| C0 | Run the relevant cell or script on a representative case; inspect shapes, finite values, ranges, and the key result |
| C1 | Add focused checks for changed formulas, units, limiting behavior, budgets, representative deterministic runs, objective components, or output metadata |
| C2 | Add interface contracts, multi-consumer cases, broader regression coverage, packaging checks, and user-facing examples |
| C3 | Apply the production system's full reliability, security, deployment, compatibility, and observability gates in addition to scientific checks |

Do not use a C0 shortcut for a consequential result merely because the project is small. Do not impose C2/C3 infrastructure on a reversible C0 exploration.

## Checks by scientific surface

### Input and preprocessing

- Exercise at least one real or faithful representative input.
- Check required variables, dimensions, coordinates, units, and calendars.
- Inspect quality flags, masks, missingness, duplicate records, and valid ranges when relevant.
- Verify spatial and temporal selections on both sides of important boundaries.
- Confirm unit conversion, aggregation, interpolation, or regridding with a small known case.
- Confirm raw or authoritative input is not overwritten.

### Formula or process rate

Choose the relevant subset:

- one known-value calculation;
- zero-input and saturation or other limiting cases;
- expected sign and monotonicity;
- dimensional consistency;
- temperature, light, substrate, or inhibition response at meaningful points;
- continuity or intended threshold behavior;
- comparison with an independent hand calculation or simpler formulation.

Do not create exhaustive combinatorial edge tests when one or two cases distinguish the plausible mistakes.

### Coupled BGC system

- Run a short deterministic 0D or box case when local processes changed.
- Check the relevant elemental, mass, charge, DIC, or alkalinity budget with external fluxes accounted for.
- Check diagnostic identities, such as a net rate equaling its documented component sum.
- Inspect physical-range or non-negativity expectations only where the numerical formulation promises them.
- Distinguish numerical drift from an intended open-system source or sink.
- Add a spatial or transport case only when the changed conclusion depends on spatial coupling.

### Solver and numerics

- Compare against an analytic, quasi-analytic, or deliberately simplified case when available.
- Check step-size, tolerance, or resolution sensitivity only over the range relevant to the conclusion.
- Verify convergence criteria and failure reporting.
- For stochastic methods, fix and record seeds for comparison while preserving the intended stochastic behavior.

### Objective and calibration

- Print or save interpretable objective components by dataset or variable.
- Verify parameter ordering, fixed/tunable selection, bounds, and transforms.
- Check that missing data and weights do not silently drop or dominate a dataset.
- Use sensitivity screening before expensive optimization of many interacting parameters.
- Check gradients against finite differences when a gradient-based result depends on them.
- Use multi-start or alternate initialization when local minima are plausible and consequential.
- Validate on held-out time, space, depth, treatment, or environmental regime.
- Report practical identifiability or compensating parameter behavior instead of treating one optimum as uniquely true.

Escalate to ensemble, Bayesian, or PEST++ methods only when uncertainty or inverse-problem structure is a research requirement. The escalation should not move equations and parameter meaning into opaque framework glue.

### Output and provenance

- Reopen the written artifact rather than trusting the in-memory object.
- Check variable names, dimensions, coordinates, units, missing values, and CF or project metadata.
- Verify diagnostic values correspond to the same run and parameter snapshot.
- Confirm output paths do not overwrite authoritative inputs.
- Record only provenance that can be used to reproduce or interpret the result.

## Refactor and simplification checks

When scientific behavior should remain unchanged:

1. Select a representative input and capture meaningful outputs or budgets before the edit.
2. Remove indirection or duplicate paths in small increments.
3. Compare scientific outputs within a tolerance justified by the numerical method.
4. Confirm the old path, configuration, or artifact is gone.
5. Run the same command through the final direct route.

An import test, type check, or generic unit suite cannot replace this comparison.

## Completion claims

State exactly which commands and cases ran. Distinguish source reading, synthetic checks, real-data smoke tests, and full experiments. Do not call a skipped, empty, or setup-only command a pass.

Stop when the requested result works and the checks that could falsify its scientific meaning have passed. Additional coverage, framework migration, performance tuning, and documentation are separate work unless they are current requirements.
