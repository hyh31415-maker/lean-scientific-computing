# Lean Scientific Computing

This repository contains complementary Codex Skills for scientific work that must remain researcher-controlled, auditable, and proportionate to the scientific question.

The shared principle is simple: code is experimental apparatus, not automatically the product.

## Included skills

### `scientific-probe`

[`skills/scientific-probe`](skills/scientific-probe) converts a scientific question into competing hypotheses, a discriminating observable, the smallest useful experiment, a predeclared decision rule, and a stop condition. It is designed to prevent Codex from replacing scientific inference with premature frameworks, APIs, configuration systems, and productization.

### `lean-scientific-computing`

[`skills/lean-scientific-computing`](skills/lean-scientific-computing) builds and simplifies researcher-controlled scientific software while preserving a direct, auditable path through:

```text
inputs -> preprocessing -> equations -> parameters -> calibration -> outputs
```

It defaults new projects to a reproducible-study level rather than a production-service architecture. Databases, workflow engines, generic coupling interfaces, compatibility layers, and service infrastructure are added only when a current requirement earns them.

The two Skills are complementary: `scientific-probe` determines what mechanism or discriminator to test; `lean-scientific-computing` implements the resulting experiment with proportional structure and scientific verification.

## What they are for

- hypothesis tests, mechanism probes, replications, and model comparisons;
- scientific scripts, notebooks, simulations, and ensembles;
- parameter estimation and inverse problems;
- oceanography, remote sensing, microbiology, carbon cycling, and BGC models;
- simplifying overengineered research repositories while preserving scientific results;
- making data selection, formulas, parameters, objectives, diagnostics, and provenance easy to audit.

## Install

Ask Codex to install either Skill directly from its folder.

```text
Install the scientific-probe skill from
https://github.com/hyh31415-maker/lean-scientific-computing/tree/main/skills/scientific-probe
```

```text
Install the lean-scientific-computing skill from
https://github.com/hyh31415-maker/lean-scientific-computing/tree/main/skills/lean-scientific-computing
```

Alternatively, copy the desired folder under `skills/` into your Codex skills directory, normally `$CODEX_HOME/skills` or `~/.codex/skills`, then start a new task so the skill catalog refreshes.

Automatic invocation is enabled for both Skills. Explicit invocation is available as `$scientific-probe` and `$lean-scientific-computing`.

## Example requests

```text
Use $scientific-probe to test whether the observed oscillation is numerical
instability or a physical mechanism. Define the cheapest discriminating run and
stop when the predeclared decision rule can be evaluated.
```

```text
Use $lean-scientific-computing to add a temperature-dependent remineralization
term to this BGC model and verify the relevant carbon budget.
```

```text
Use $scientific-probe to audit this research repository. Trace the shortest
scientific dependency chain to the reported figure and identify removable
engineering overhead without weakening reproducibility.
```

```text
Use $lean-scientific-computing to simplify this research pipeline. Preserve the
scientific outputs and leave one direct route from the input catalog to results.
```

## Design basis

The Skills promote transferable lessons from scientific-computing practice and mature research projects without copying project-specific infrastructure:

- [Good enough practices in scientific computing](https://doi.org/10.1371/journal.pcbi.1005510)
- [MARBL](https://marbl.readthedocs.io/en/latest/dev-guide/introduction.html)
- [FABM](https://github.com/fabm-model/fabm)
- [OceanBioME](https://github.com/OceanBioME/OceanBioME.jl)
- [AIBECS](https://github.com/JuliaOcean/AIBECS.jl)
- [CF Conventions](https://cfconventions.org/)
- [STAC](https://stacspec.org/)

Behavioral evaluation material is stored with each Skill:

- [`scientific-probe` evals](skills/scientific-probe/evals)
- [`lean-scientific-computing` behavioral evals](skills/lean-scientific-computing/references/behavioral-evals.md)

## License

MIT
