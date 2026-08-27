# Lean Scientific Computing

`lean-scientific-computing` is a Codex Skill for building researcher-controlled scientific software without letting project machinery obscure the science.

It keeps a direct, auditable path through:

```text
inputs -> preprocessing -> equations -> parameters -> calibration -> outputs
```

The Skill defaults new researcher-controlled projects to a reproducible-study level rather than a production-service architecture. Databases, workflow engines, generic coupling interfaces, compatibility layers, and service infrastructure are added only when a current requirement earns them.

## What it is for

- scientific scripts, notebooks, simulations, and ensembles;
- parameter estimation and inverse problems;
- oceanography, remote sensing, microbiology, carbon cycling, and BGC models;
- simplifying overengineered research repositories while preserving scientific results;
- making data selection, formulas, parameters, objectives, diagnostics, and provenance easy to audit.

It complements hypothesis-oriented workflows such as `exploratory-science`: exploration decides what mechanism or discriminator to pursue; this Skill implements it with proportional structure and verification.

## Install

Ask Codex:

```text
Install the lean-scientific-computing skill from
https://github.com/hyh31415-maker/lean-scientific-computing/tree/main/skills/lean-scientific-computing
```

Or copy `skills/lean-scientific-computing` into your Codex skills directory, normally `$CODEX_HOME/skills` or `~/.codex/skills`, then start a new task so the skill catalog refreshes.

Automatic invocation is enabled by default. You can invoke it explicitly with `$lean-scientific-computing`.

## Example requests

```text
Use $lean-scientific-computing to add a temperature-dependent remineralization
term to this BGC model and verify the relevant carbon budget.
```

```text
Use $lean-scientific-computing to simplify this research pipeline. Preserve the
scientific outputs and leave one direct route from the input catalog to results.
```

```text
Use $lean-scientific-computing to organize calibration of these model parameters
without introducing an experiment-management platform.
```

## Design basis

The Skill promotes transferable lessons from mature scientific-computing practice and real marine biogeochemistry projects, without copying their project-specific infrastructure:

- [Good enough practices in scientific computing](https://doi.org/10.1371/journal.pcbi.1005510)
- [MARBL](https://marbl.readthedocs.io/en/latest/dev-guide/introduction.html)
- [FABM](https://github.com/fabm-model/fabm)
- [OceanBioME](https://github.com/OceanBioME/OceanBioME.jl)
- [AIBECS](https://github.com/JuliaOcean/AIBECS.jl)
- [CF Conventions](https://cfconventions.org/)
- [STAC](https://stacspec.org/)

The behavioral evaluation cases are in [`references/behavioral-evals.md`](skills/lean-scientific-computing/references/behavioral-evals.md).

## License

MIT
