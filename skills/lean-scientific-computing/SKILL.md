---
name: lean-scientific-computing
description: Build, modify, simplify, or organize researcher-controlled scientific computing with minimal transparent structure, proportional scientific verification, and direct traceability from inputs through equations and parameters to outputs. Use for research scripts, notebooks, simulations, calibration, ensembles, and ocean, remote-sensing, microbial, carbon-cycle, or BGC models, especially when overengineering would obscure the science. Do not use as the primary workflow for hypothesis generation, formal code review, or customer-facing operational systems.
---

# Lean Scientific Computing

## Outcome contract

Deliver the smallest transparent implementation that answers the current scientific task and preserves its scientific meaning. Optimize for traceability, reproducibility, and ease of inspection by the researcher and their future self—not for the fewest lines and not for imagined future users.

Keep one direct path from inputs to scientific results. Make data selection, equations, parameters, objectives, diagnostics, and assumptions easier to locate than the surrounding infrastructure. Add complexity only after a present requirement earns it.

Match the user's requested depth. Do not pad the work with generic cautions, broad project-management ceremonies, or exhaustive edge-case machinery.

## Route within the skill system

Use this skill as the primary implementation workflow for researcher-controlled scientific computation.

- Use `exploratory-science` when the task is choosing hypotheses, extrapolating from sparse evidence, or selecting the next discriminating study. Return here when that choice becomes data, model, calibration, or output work.
- Use `scientific-visualization` for quantitative figures, maps, or ocean diagnostics.
- Use `project-keeper` for starting, splitting, pausing, resuming, or organizing projects and workspaces.
- Use `hunt` for root-cause diagnosis of broken behavior.
- Use `check` for a formal review, audit, release, or publication gate.
- Use normal production-engineering workflows when a system is customer-facing, operationally critical, or externally hosted.

Do not invoke adjacent skills pre-emptively. Route only the operation that needs them.
Treat these as optional integrations, not dependencies. If a named skill is unavailable, keep the current task self-contained or use the environment's equivalent workflow.

## Core decision loop

1. **Infer the project level.** Preserve the existing repository's conventions. For a new researcher-controlled project, default to C1; do not ask the user to classify it unless the choice materially changes the work.
2. **Name the scientific surface.** Identify which of these actually changes: input catalog, preprocessing, scientific core, parameter system or objective, solver/calibration, diagnostics/output, or project infrastructure.
3. **Bound the edit.** Work only on the requested surface and the smallest set of directly affected consumers and scientific checks. Do not turn a local change into a repository redesign.
4. **Apply the complexity gate.** Before adding a dependency, top-level directory, generic interface, registry, plugin system, database, workflow engine, compatibility layer, service, or second control path, use the gate below.
5. **Implement the direct route.** Prefer explicit functions, data structures, configurations, and drivers whose scientific ownership is obvious. Reuse existing libraries and project conventions when they already solve the task.
6. **Exercise representative reality early.** Run one real or realistic input through the changed path before building generalized machinery around it.
7. **Verify the scientific consequence.** Select the smallest checks that can detect a wrong scientific result, not a generic test quota.
8. **Simplify and stop.** Remove superseded paths and unearned structure, report the science delta and checks actually run, then stop without adjacent cleanup.

Read [references/project-levels-and-complexity.md](references/project-levels-and-complexity.md) when creating or restructuring a project, simplifying an overbuilt repository, or considering a new abstraction, dependency, data store, workflow system, or coupling interface. Read [references/scientific-spine.md](references/scientific-spine.md) when changing inputs, equations, parameters, calibration, provenance, or outputs. For oceanography, biogeochemistry, remote sensing, microbial processes, or organic carbon, also read [references/ocean-bgc-and-earth-observation.md](references/ocean-bgc-and-earth-observation.md). Read [references/scientific-verification.md](references/scientific-verification.md) when selecting checks or changing calibration. Read [references/behavioral-evals.md](references/behavioral-evals.md) only when testing or revising this skill.

## Complexity gate

For a proposed permanent mechanism, ask:

1. Does it solve a current requirement, observed failure, or measured bottleneck?
2. Can a local function, file, table, or configuration solve the same problem clearly?
3. Does it reduce total concepts, duplication, or hidden scientific meaning rather than merely relocate complexity?
4. For a generic abstraction, are there already two real variants or consumers, or one fixed external contract?
5. If the choice is wrong, is it easy to remove?

The first three must support the addition; apply the fourth to generic abstractions. Otherwise keep the solution local. A possibly useful future idea may be mentioned once with its activation condition, but do not create machinery, a backlog, or a design document for it.

## Scientific uncertainty and blocking

When evidence is incomplete but the implementation is reversible, choose the best current working assumption, localize it in an explicit parameter, equation, or experiment configuration, and continue. State it once where it affects interpretation.

Do not let a non-blocking detail hold the main task. Pause only when alternatives would materially change scientific meaning, units, conservation, an irreversible data transformation, the objective function, external cost, or a destructive action. Do not ask the user to settle an assumption that can be tested downstream at low cost.

## Scientific code preferences

- Prefer a small explicit scientific core over factories, dependency injection, plugin registries, or generic orchestration.
- Keep raw or authoritative inputs unchanged; make preprocessing reproducible and separately identifiable.
- Give model parameters one authoritative registry. Do not duplicate defaults and bounds across code and configuration.
- Keep calibration outside the scientific process equations unless the existing project has a clear reason not to.
- Expose meaningful intermediate rates, fluxes, residuals, or budgets as diagnostics instead of recomputing them in reporting code.
- Treat data catalogs, workflow engines, coupling standards, and databases as escalation options, not defaults.
- Do not reorganize an existing project merely to match an example layout.

## Verification and completion

Choose checks by the changed scientific surface: representative input, dimensions and units, known values, limiting behavior, sign or monotonicity, elemental or mass budgets, a small deterministic run, objective decomposition, held-out regimes, or output metadata. Run only the relevant subset, but do not substitute broad generic tests for a missing scientific check.

For a substantive change, hand off a compact science diff:

- scientific behavior changed: touched inputs, equations/processes, parameters/objective, and outputs;
- infrastructure changed: only additions that passed the complexity gate;
- verification: commands and scientific checks actually run;
- deferred: only real non-blocking items with a condition that would reactivate them.

For a small task, answer directly without forcing this template. Completion means the requested behavior works, relevant scientific checks pass, superseded mechanisms are gone, and no additional structure is needed for the current result.
