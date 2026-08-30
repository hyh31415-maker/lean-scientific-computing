---
name: lean-scientific-computing
description: Implement, run, or simplify researcher-controlled scientific computation when the scientific target is already defined. Use for scoped scripts, notebooks, simulations, calibration, ensembles, data preparation, BGC or Earth-observation models, and behavior-preserving repository simplification. Preserve any scientific-probe contract and keep inputs, equations, parameters, numerics, and outputs traceable. Do not use to choose hypotheses, interpret unresolved evidence, review, debug, visualize, manage workspaces, or design operational services.
license: MIT
metadata:
  author: hyh31415-maker
  version: "0.2.0"
  suite: lean-scientific-research
  role: scientific-implementation
---

# Lean Scientific Computing

## Outcome contract

Deliver the smallest transparent implementation that answers the current scientific task and preserves its meaning. Optimize for traceability, reproducibility, and researcher inspection—not minimum line count or imagined future users.

Keep one authoritative execution and configuration-resolution path per distinct result. Simulation, calibration, sensitivity, and validation may have separate thin entrypoints; they must share scientific definitions rather than duplicate them.

Match the requested depth. Omit generic cautions, project ceremony, and exhaustive edge-case machinery.

## Boundary and handoff

Use this Skill when the scientific behavior or probe is already specified and the remaining work is implementation, execution, scientific checking, or scoped simplification.

If the main work is broad hypothesis formation or research-direction choice, keep it in the exploratory-science workflow when available. If a framed target needs a frozen discriminator, replication rule, or bounded anomaly probe, use `$scientific-probe` first. For mixed work, use one sequence:

```text
Probe Contract -> lean implementation -> Evidence Record -> scientific interpretation
```

Do not emit a second research plan or bounce between Skills for local reversible details. If the sibling Skill is unavailable, preserve the same boundary locally.

When a Probe Contract exists, preserve its mode, target, population, sample-changing preprocessing, controls, primary observable, analysis or branch rule, seed policy when consequential, stop rule, and required raw artifacts. Confirmatory fields must not change silently after results are seen. Discovery branches may adapt only when retained and labeled exploratory.

For an already specified local change, use a compact internal brief instead of manufacturing a contract:

```text
requested behavior | touched scientific surface | representative case | checks | stop condition
```

## Core decision loop

1. **Inspect the existing route.** Locate authoritative inputs, preprocessing, equations, parameter resolution, execution entrypoint, and reported outputs before editing.
2. **Choose the lowest adequate level.** Preserve repository conventions. A stated prototype is normally C0; use C1 when a result must be rerun, compared, cited, shared, or defended. A new project alone does not earn C1.
3. **Bound the edit.** Modify the requested surface, direct consumers, and result-protecting checks. Do not inspect or clean unrelated architecture.
4. **Apply the complexity gate.** Require a present scientific or operational obligation before adding permanent machinery.
5. **Implement one direct route.** Prefer explicit functions, data, parameter resolution, and thin result drivers with obvious scientific ownership.
6. **Exercise proportional reality.** Use the smallest representative data and shortest non-empty run that can expose a wrong result. Full production data, paid resources, remote scheduling, long optimization, or large ensembles require an explicit current-task request.
7. **Verify the scientific consequence and stop.** Remove only paths made unused by this change; report what changed and what actually ran.

Read [references/project-levels-and-complexity.md](references/project-levels-and-complexity.md) for project creation, restructuring, simplification, or new permanent machinery. Read [references/scientific-spine.md](references/scientific-spine.md) for inputs, equations, parameters, objectives, calibration, provenance, or outputs. Read [references/scientific-verification.md](references/scientific-verification.md) when selecting checks or changing numerics, calibration, outputs, or performance. For oceanography, BGC, remote sensing, microbial processes, or organic carbon, also read [references/ocean-bgc-and-earth-observation.md](references/ocean-bgc-and-earth-observation.md). Read [references/behavioral-evals.md](references/behavioral-evals.md) only when revising or evaluating this Skill.

## Complexity gate

Add a permanent dependency, directory, abstraction, registry, data store, workflow system, compatibility layer, service, or second control path only when every applicable condition holds:

1. A current requirement, observed failure, or measured bottleneck exists.
2. A simpler local function, file, table, or configuration is insufficient.
3. The mechanism reduces total concepts, duplication, or hidden scientific meaning rather than relocating complexity.
4. A generic abstraction has real consumers or variants, or one fixed external contract.
5. The decision has a clear removal or reversal path if its assumption fails.

Apply item 4 only to generic abstractions. Do not add future-facing flags, placeholders, backlogs, or design documents. C2/C3 obligations may legitimately earn mature engineering; minimalism must not hide them.

## Scientific uncertainty and invariants

Continue with a working assumption when the user, repository, Probe Contract, or a verified source specifies or reasonably implies it. Record it once in the owning equation, parameter definition, or experiment configuration.

Do not silently choose alternatives that could change the conclusion, including rate or temperature-response forms, dimensions or scaling, observation operators, objective weights, priors, and open or closed boundaries. When cheap, encode explicit experiment alternatives; otherwise pause only the affected branch and report the choice required.

- Keep authoritative inputs unchanged and preprocessing reproducible.
- Use one resolution chain per scientific semantic. Base definitions, experiment overrides, and resolved run snapshots are valid layers when one resolver owns precedence.
- Keep equations and process rates inspectable; keep calibration outside them when practical; expose diagnostics from their scientific owner.
- Fail visibly rather than apply a fallback that changes the scientific population, units, equation, or objective.
- Treat databases, workflow engines, coupling standards, and services as earned escalation options, never as default scaffolding.

## Verification and Evidence Record

Use the fewest checks capable of falsifying the changed scientific meaning or exposing contract drift. Generic imports, lint, type checks, or coverage do not replace formula, unit, limit, budget, representative-run, leakage, objective, sensitivity, or output-reopen checks when those are relevant.

Keep claims distinct: **verification** concerns declared equations and numerics; **validation** concerns independent observations; **calibration diagnostics** concern inference behavior. One does not prove the others.

For substantive work, return a compact Evidence Record containing the relevant contract or implementation brief, declared deviations, commands or cells actually run, input identity and preprocessing, parameters/seeds/numerics when consequential, raw artifacts and branch logs, observed outputs and failed runs, scientific checks, files changed, and the stop condition reached. Label the run `confirmatory`, `exploratory`, `feasibility-only`, or `invalid`. Small deterministic tasks may be reported directly.

## Completion

Completion means the requested behavior works, frozen scientific meaning was preserved or deviations were declared, relevant checks ran or failures were reported, one authoritative route remains, and no additional structure is required by the current obligation.

Stop without unsolicited refactoring, packaging, performance tuning, dashboards, APIs, broad sweeps, or product documentation.
