---
name: lean-scientific-computing
description: Implement, run, verify, or simplify an already-defined researcher-controlled scientific computation through one traceable path from inputs and equations to outputs. Use for scientific scripts, simulations, calibration, diagnostics, data preparation, BGC or Earth-observation models, 科研代码、模型实现、科研仓库精简, and de-bloating research repositories. Preserve a scientific-probe Probe Contract and label discovery branches as exploratory. Do not use to choose hypotheses or interpret unresolved evidence; use scientific-probe first.
license: MIT
metadata:
  author: hyh31415-maker
  version: "0.2.0"
  suite: lean-scientific-research
  role: scientific-implementation
---

# Lean Scientific Computing

## Mission

Deliver the smallest transparent implementation that produces trustworthy scientific evidence for the current task.

Optimize for traceability, reproducibility, and ease of inspection by the researcher—not minimum line count, generic reuse, or imagined future users. Keep one direct path from authoritative inputs through preprocessing, equations, parameters, solver or calibration, diagnostics, and outputs.

## Scope and routing

Use this Skill when the scientific target is sufficiently defined and the remaining work is computational:

- implement a specified equation, parameterization, objective, or diagnostic;
- prepare a defined dataset or observation operator;
- run a planned confirmatory test, discovery branch, simulation, calibration, comparison, or ensemble;
- verify scientific behavior with meaningful checks;
- simplify an overengineered research repository while preserving declared evidence.

Use `$scientific-probe` first when the primary question is whether an effect exists, which mechanism explains it, what unexpected result to pursue, what observation would distinguish alternatives, what replication should count as, or what the evidence justifies.

For mixed work, follow one sequence:

```text
Probe Contract -> lean implementation -> Evidence Record -> scientific interpretation
```

Do not emit a second independent research plan or repeatedly hand off for local reversible details. If `$scientific-probe` is unavailable, preserve the same contract boundary locally.

## Accept the scientific contract

### When a Probe Contract exists

Treat it as the experiment specification. Preserve:

- mode and scientific target;
- current alternatives and discriminating prediction or discovery signal;
- population, exclusions, and sample-changing preprocessing;
- controls;
- primary observable or statistic;
- analysis, decision, branch, and stop rules;
- seed or initialization policy when consequential;
- required raw artifacts and provenance.

Mode-specific handling:

- **DISCRIMINATION / REPLICATION:** do not silently optimize, broaden, or improve frozen fields after seeing the result.
- **DISCOVERY:** implement bounded adaptive branches when the contract allows them; retain every branch, failed attempt, metric change, and selection rule; classify all such runs as exploratory.

If implementation reality makes a field impossible or invalid, declare the smallest necessary deviation before the affected run when possible. Do not silently substitute a new scientific question. A changed confirmatory rule requires a new contract before it can support confirmatory evidence.

### When no Probe Contract is needed

For an already specified deterministic implementation, form a compact internal brief:

```text
Requested scientific behavior:
Scientific surface touched:
Representative case:
Scientific checks:
Stop condition:
```

Do not manufacture hypotheses, thresholds, or ceremony for a local change.

## Core loop

1. **Inspect the existing route.** Find authoritative inputs, preprocessing, equations, parameter source, execution entry, and reported outputs before editing.
2. **Infer project maturity.** Use C0–C3 from [references/project-levels-and-complexity.md](references/project-levels-and-complexity.md). Research phase and project maturity are independent.
3. **Name the scientific surface.** Limit work to the smallest affected surface and direct consumers: input, preprocessing, scientific core, parameter/objective, solver/calibration, diagnostics/output, or infrastructure.
4. **Bound the edit.** Do not turn a local scientific change into a repository redesign.
5. **Apply the complexity gate.** Require a present scientific or operational obligation for every permanent mechanism.
6. **Implement one direct route.** Prefer explicit functions, data structures, and experiment drivers whose scientific ownership is obvious.
7. **Exercise representative reality early.** Run one real or faithful input through the changed path before generalized machinery.
8. **Verify the scientific consequence.** Choose checks capable of revealing a wrong scientific result or contract drift.
9. **Produce the Evidence Record.** Return observations, failures, branches, and artifacts without overstating meaning.
10. **Simplify and stop.** Remove superseded paths and avoid adjacent cleanup or productization.

Read [references/scientific-spine.md](references/scientific-spine.md) when changing inputs, preprocessing, equations, parameters, objectives, calibration, provenance, diagnostics, or outputs. Read [references/scientific-verification.md](references/scientific-verification.md) when selecting checks. Read [references/project-levels-and-complexity.md](references/project-levels-and-complexity.md) when creating, restructuring, simplifying, or promoting a project. For oceanography, aquatic biogeochemistry, remote sensing, microbial processes, or organic carbon, also read [references/ocean-bgc-and-earth-observation.md](references/ocean-bgc-and-earth-observation.md).

## Complexity gate

Before adding a dependency, top-level directory, generic interface, registry, plugin system, database, workflow engine, compatibility layer, service, second control path, or broad test hierarchy, ask:

1. Which current scientific or operational requirement does it own?
2. Why cannot a local function, file, table, or configuration satisfy that requirement clearly?
3. Does it reduce total concepts or expose scientific meaning rather than relocate complexity?
4. For a generic abstraction, are there already two real variants or consumers, or one fixed external contract?
5. If the assumption is wrong, can the mechanism be removed cleanly?

The first three must support the addition; apply the fourth to generic abstractions. Otherwise keep the solution local.

C2 or C3 obligations can legitimately earn packaging, interfaces, orchestration, services, security, monitoring, and compatibility work. Minimalism must not hide real obligations.

## Scientific code preferences

- Keep raw or authoritative inputs unchanged; make transformations reproducible and visible.
- Fail visibly rather than apply a fallback that changes the scientific population, units, equation, or objective.
- Maintain one authoritative source for parameter values, units, bounds, transforms, and tunability.
- Keep equations and process rates inspectable; do not bury them in factories or serialization glue.
- Keep calibration and objectives explicit and decomposable.
- Expose meaningful intermediate rates, fluxes, residuals, and budgets from their owning computation.
- Prefer a direct call or thin adapter until a second real host or fixed external contract earns an interface.
- Do not reorganize a repository merely to match an example layout.
- Allow limited explicit duplication when abstraction would hide causal or scientific ownership.
- Keep exploratory branches in a scratch area or explicit run table; do not build a permanent experiment platform for one search.

## Verification

Select the smallest checks that can falsify the changed scientific meaning or reveal contract drift:

- representative real or faithful inputs;
- units, dimensions, ranges, missingness, and sample identity;
- known values and limiting behavior;
- sign, monotonicity, continuity, or thresholds;
- conservation or elemental budgets;
- deterministic toy or box runs;
- leakage-resistant splits;
- objective decomposition and parameter ordering;
- seed, tolerance, resolution, or initialization sensitivity when consequential;
- reopening saved output and checking metadata;
- confirming that all exploratory branches and failed runs were retained.

Generic imports, lint, type checks, or coverage do not replace these checks. State exactly what ran. Never report skipped, empty, synthetic-only, partial, or setup-only work as stronger evidence than it is.

## Simplifying an overengineered research repository

Repository simplification belongs here.

1. Freeze the scientific result or Evidence Record that must survive.
2. Trace the shortest live dependency chain from authoritative inputs and assumptions to that result.
3. Classify surrounding components as scientific core, reproducibility support, currently earned engineering, removable overhead, or unknown.
4. Collapse one unearned seam at a time.
5. Delete superseded routes in the same change; do not leave parallel loaders, parameter sources, run paths, or configuration owners.
6. Re-run the scientific comparison within an explicit tolerance.
7. Prefer deletion and consolidation over replacement-framework rewrites.

Do not remove provenance, raw outputs, unit conversion, randomization, blinding, numerical stability controls, exploration logs, or scientific checks merely because they are verbose.

## Evidence Record

For substantive work, return:

```text
Mode and scientific target:
Run classification: confirmatory / exploratory / feasibility-only / invalid
Contract or implementation brief preserved:
Declared deviations:
Commands or cell sequence actually run:
Code revision and relevant environment:
Input identity, population, preprocessing, and provenance:
Seeds, initialization, solver, or tolerances when relevant:
Raw artifact and exploration-log locations:
[observed] Primary outputs, controls, branches, and failed runs:
Scientific checks and failures:
Files changed and the scientific role of each:
Engineering added and the current requirement that earned it:
Engineering deliberately omitted:
Stop condition reached:
```

Keep interpretation bounded. Report direct observations and implementation-dependent facts. When the user asks what the result means, pass this record back to `$scientific-probe` or apply its evidence discipline explicitly.

For a small deterministic task, answer directly without forcing the full template.

## Completion

Completion means:

- the requested scientific behavior works;
- the mode-appropriate contract or implementation brief was preserved or deviations were declared;
- exploratory branches remain complete and labeled;
- relevant scientific checks passed or failures were reported;
- the authoritative route is easier, not harder, to trace;
- superseded mechanisms are gone;
- no additional structure is required for the current obligation.

Stop without unsolicited refactoring, packaging, performance tuning, dashboards, APIs, or product documentation.

Read [references/behavioral-evals.md](references/behavioral-evals.md) only when revising or evaluating this Skill.
