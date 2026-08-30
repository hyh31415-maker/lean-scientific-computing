# Lean Scientific Research for Codex

[中文说明](README.zh-CN.md)

This repository packages two coordinated Codex Skills for exploratory science and researcher-controlled computation:

- [`scientific-probe`](skills/scientific-probe) freezes and interprets one bounded probe after the scientific target is framed.
- [`lean-scientific-computing`](skills/lean-scientific-computing) implements or simplifies the code path needed to obtain that evidence.

They share one rule:

> Be adventurous in hypotheses, conservative in claims, and proportional in engineering.

The Skills stay separate because inquiry design and implementation have different triggers and stopping rules. They exchange a compact contract only when ownership changes; local reversible details do not require a handoff.

## Coordinated workflow

```text
open-ended frontier (optional exploratory-science)
        -> framed question, candidates, or scoped anomaly
        -> scientific-probe: Probe Contract
        -> lean-scientific-computing: Evidence Record
        -> scientific-probe: interpretation / branch / stop
        -> product engineering only when a current obligation requires it
```

| Request | Primary workflow |
|---|---|
| Explore a broad hypothesis space or choose a research direction | `exploratory-science` when installed; otherwise ordinary exploratory reasoning |
| Turn a scoped anomaly into one logged adaptive probe | `scientific-probe` in DISCOVERY mode |
| Distinguish credible alternatives | `scientific-probe` in DISCRIMINATION mode |
| Define and rerun a replication | `scientific-probe` in REPLICATION mode, then implementation as needed |
| Implement a specified equation, dataset transformation, calibration, or diagnostic | `lean-scientific-computing` |
| Run a frozen comparison and preserve its controls | `lean-scientific-computing`, then `scientific-probe` for interpretation |
| Simplify an overengineered research repository without changing its result | `lean-scientific-computing` |
| Deploy an already validated model with real security, uptime, or compatibility obligations | Normal production engineering |

See [`docs/coordination.md`](docs/coordination.md) for ownership, contract integrity, and anti-loop rules.

## Discovery is not forced into confirmation

`scientific-probe` selects the mode after a bounded target exists:

- **DISCOVERY** permits bounded, logged adaptation for a scoped anomaly or search target. Selected branches remain exploratory.
- **DISCRIMINATION** freezes the primary discriminator and decision rule for one comparison.
- **REPLICATION** freezes the evaluated population, preprocessing, statistic, success/failure rule, and stop condition before rerunning a claim.

A Probe Contract freezes one probe, not the whole research program. Surprising evidence may create a new branch and contract; it must not be hidden by post-result changes to the original rule.

If the separate `exploratory-science` Skill is installed, it owns open-ended sensemaking and hypothesis portfolios. `scientific-probe` begins only when one scoped probe benefits from a frozen contract; a quick reversible exploration does not need an extra handoff.

## Proportional scientific computing

`lean-scientific-computing` keeps an inspectable route through:

```text
inputs -> preprocessing -> equations -> parameters -> numerics -> outputs
```

Each distinct scientific result gets one authoritative execution and configuration-resolution path. Simulation, calibration, sensitivity, and validation may retain separate thin entrypoints while sharing the same scientific core. Databases, workflow engines, services, generic interfaces, and compatibility layers are added only when a current scientific or operational obligation earns them.

Focused references cover project maturity, the scientific spine, verification, and ocean/BGC/Earth-observation work. They are loaded only when relevant.

## Invocation

Implicit invocation is enabled for both Skills, so Codex may select the matching workflow from an ordinary request. Explicit `$scientific-probe` and `$lean-scientific-computing` invocation remains available when you want to force a boundary or mode.

## Install

Ask Codex to install the two GitHub Skill directories with `$skill-installer`:

```text
Install scientific-probe from
https://github.com/hyh31415-maker/lean-scientific-computing/tree/main/skills/scientific-probe

Install lean-scientific-computing from
https://github.com/hyh31415-maker/lean-scientific-computing/tree/main/skills/lean-scientific-computing
```

For a repository-scoped manual installation:

```bash
mkdir -p .agents/skills
cp -R skills/scientific-probe .agents/skills/
cp -R skills/lean-scientific-computing .agents/skills/
```

For a user account, use the Skill directory scanned by that Codex installation. Current installations commonly use `~/.agents/skills`; configured or older setups may use `$CODEX_HOME/skills` or `~/.codex/skills`. Install one copy of each name because duplicate Skill names are not merged.

The repository also includes [`.codex-plugin/plugin.json`](.codex-plugin/plugin.json), allowing both Skills to be distributed as one plugin bundle while retaining separate activation boundaries.

For persistent repository routing, copy the concise rules in [`templates/AGENTS.md`](templates/AGENTS.md) into the target repository's `AGENTS.md` only when that project benefits from the shared workflow.

## Evaluation status

The repository contains per-Skill cases and cross-Skill routing rubrics. They define reproducible behavioral tests; they are not claims that every model or host has already passed. A valid run record must preserve the prompt, fixture, model and reasoning settings, permissions, diff, commands, outputs, and reviewer decision.

## Design basis

The implementation Skill draws transferable lessons from scientific-computing practice and mature marine-biogeochemistry projects without copying their project-specific infrastructure:

- [Good enough practices in scientific computing](https://doi.org/10.1371/journal.pcbi.1005510)
- [MARBL](https://marbl.readthedocs.io/en/latest/dev-guide/introduction.html)
- [FABM](https://github.com/fabm-model/fabm)
- [OceanBioME](https://github.com/OceanBioME/OceanBioME.jl)
- [AIBECS](https://github.com/JuliaOcean/AIBECS.jl)
- [CF Conventions](https://cfconventions.org/)
- [STAC](https://stacspec.org/)

## License

MIT
