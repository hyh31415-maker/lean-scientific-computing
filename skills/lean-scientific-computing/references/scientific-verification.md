# Scientific Verification

Read this reference when selecting checks, modifying scientific behavior, changing calibration or optimization, or producing an Evidence Record.

Verification is proportional to the scientific consequence. The goal is to expose a wrong result with the fewest meaningful checks, not to maximize test count or coverage.

When a Probe Contract exists, verification must show that implementation preserved the mode-appropriate controls, scientific population, primary observable, analysis or branch rule, and stop condition. For DISCOVERY, it must also show that all branches, failed attempts, and metric changes remain recorded and exploratory.

## Verification by project level

| Level | Minimum useful evidence |
|---|---|
| C0 | Run the relevant cell or script on a representative case; inspect shapes, finite values, ranges, controls, the primary result, and branch log when exploratory |
| C1 | Add focused checks for formulas, units, limiting behavior, budgets, representative deterministic runs, objective components, provenance, or output metadata |
| C2 | Add interface contracts, multi-consumer cases, broader regression coverage, packaging checks, and user-facing examples |
| C3 | Apply full reliability, security, deployment, compatibility, and observability gates in addition to scientific checks |

Do not use a C0 shortcut for a consequential result merely because the project is small. Do not impose C2/C3 infrastructure on a reversible C0 probe.

## Checks by scientific surface

### Input and preprocessing

- Exercise at least one real or faithful representative input.
- Check required variables, dimensions, coordinates, units, calendars, and valid ranges.
- Inspect flags, masks, missingness, duplicates, and boundary selections.
- Verify conversion, aggregation, interpolation, or regridding with a small known case.
- Confirm authoritative input is not overwritten.
- Confirm preprocessing matches frozen population and exclusion rules for confirmatory work; retain all sample-changing discovery branches.

### Formula or process rate

Choose the relevant subset:

- one known-value calculation;
- zero-input, saturation, or other limiting cases;
- expected sign and monotonicity;
- dimensional consistency;
- response at scientifically meaningful points;
- continuity or intended threshold behavior;
- independent hand calculation or simpler formulation.

One or two discriminating cases are better than an exhaustive generic edge matrix.

### Coupled scientific system

- Use a short deterministic toy, box, or reduced case when local processes changed.
- Check relevant mass, elemental, charge, DIC, alkalinity, energy, or probability budgets with external terms accounted for.
- Check diagnostic identities and component sums.
- Distinguish numerical drift from intended open-system sources and sinks.
- Add spatial or transport cases only when the conclusion depends on spatial coupling.

### Solver and numerics

- Compare against analytic, quasi-analytic, or deliberately simplified cases when available.
- Check step size, tolerance, or resolution only over the range relevant to the decision.
- Verify convergence criteria and failure reporting.
- Record seeds while preserving intended stochastic behavior.
- Do not tune numerical settings after seeing the desired answer without reporting the deviation. Keep discovery tuning branches complete rather than only the favorable run.

### Objective and calibration

- Save interpretable objective components.
- Verify parameter ordering, fixed/tunable selection, bounds, and transforms.
- Check that missingness and weights do not silently drop or dominate data.
- Screen sensitivity before expensive optimization of many interacting parameters.
- Check gradients when the conclusion depends on them.
- Use multi-start or alternative initialization when local minima are consequential.
- Validate on held-out regimes defined before result inspection.
- Report practical non-identifiability instead of treating one optimum as uniquely true.

Escalate to ensemble, Bayesian, workflow, or external inversion machinery only when it is a current research requirement.

### Output and provenance

- Reopen the written artifact rather than trusting the in-memory object.
- Check names, dimensions, coordinates, units, missing values, and metadata.
- Confirm diagnostics correspond to the same run and parameter snapshot.
- Confirm outputs do not overwrite authoritative inputs.
- Record provenance that can reproduce or interpret the result.
- Include run classification, failures, branches, and contract deviations in the Evidence Record.

## Refactor and simplification checks

When scientific behavior should remain unchanged:

1. Capture a representative Evidence Record before the edit.
2. Remove indirection or duplicate paths incrementally.
3. Compare meaningful outputs within a tolerance justified by the numerical method.
4. Confirm the old path, configuration, or artifact is gone.
5. Run the same command through the final direct route.
6. Confirm the Probe Contract or declared scientific behavior did not drift.

An import test, type check, or generic unit suite cannot replace this comparison.

## Completion claims

State exactly which commands and cases ran. Distinguish source reading, synthetic checks, real-data smoke tests, partial runs, and full experiments. Do not call a skipped, empty, or setup-only command a pass.

Stop when the requested result works and the checks capable of falsifying its scientific meaning have completed. Additional coverage, framework migration, performance tuning, and documentation are separate work unless they are current requirements.
