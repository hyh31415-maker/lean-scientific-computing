# Lean Scientific Research for Codex

[中文说明](README.zh-CN.md)

This repository packages two coordinated Codex Skills for scientific work:

- [`scientific-probe`](skills/scientific-probe) decides **what evidence could change the scientific answer**.
- [`lean-scientific-computing`](skills/lean-scientific-computing) implements or simplifies **the code path needed to obtain that evidence**.

They share one principle:

> Be adventurous in hypotheses, conservative in claims, and proportional in engineering.

The two Skills remain separate on purpose. Scientific inquiry and scientific implementation have different trigger conditions, outputs, and stopping rules. Keeping them focused improves routing while still allowing a deliberate handoff.

## Coordinated workflow

```text
unresolved question, anomaly, or claim
                 |
                 v
         $scientific-probe
            Probe Contract
                 |
                 v
   $lean-scientific-computing
            Evidence Record
                 |
                 v
         $scientific-probe
      inference / branch / stop
```

`scientific-probe` owns alternatives, discriminating predictions, analysis rules, and interpretation. `lean-scientific-computing` owns data, equations, parameters, execution, scientific verification, and repository structure.

For a task with both research and delivery work:

```text
probe -> lean implementation -> evidence interpretation -> optional product engineering
```

Do not build a product layer merely to discover whether the scientific effect exists.

## Discovery is not forced into confirmation

`scientific-probe` selects one of three modes:

- **DISCOVERY** — expand a poorly specified hypothesis space, seek anomalies, and run bounded adaptive probes. Exploratory branches are logged rather than presented as confirmatory evidence.
- **DISCRIMINATION** — compare credible alternatives using a frozen primary discriminator and rule.
- **REPLICATION** — define the population, exclusions, statistic, success/failure rule, and stop condition before rerunning a claim.

A Probe Contract freezes one probe, not the entire research program. Surprising evidence may generate a new contract and a new branch; it must not be hidden by post-result metric or threshold changes.

## Which Skill should run?

| Request | Primary workflow |
|---|---|
| “What non-obvious mechanisms could explain this anomaly?” | `$scientific-probe` in DISCOVERY mode |
| “What is the cheapest experiment that distinguishes A from B?” | `$scientific-probe` in DISCRIMINATION mode |
| “Reproduce this result, with failure defined in advance.” | `$scientific-probe`, then implementation as needed |
| “Add this specified rate law to the model.” | `$lean-scientific-computing` |
| “Run this frozen comparison and preserve its controls.” | `$lean-scientific-computing`, then `$scientific-probe` for interpretation |
| “Simplify this overengineered research repository without changing results.” | `$lean-scientific-computing` |
| “Build a service for a new method, but first show it beats the baseline.” | Probe -> lean implementation -> interpretation -> normal product engineering |
| “Deploy this already validated model with uptime and security requirements.” | Normal production engineering |

See [`docs/coordination.md`](docs/coordination.md) for ownership, handoff integrity, and anti-loop rules.

## Install both Skills locally

For a repository:

```bash
mkdir -p .agents/skills
cp -R skills/scientific-probe .agents/skills/
cp -R skills/lean-scientific-computing .agents/skills/
```

For a user account:

```bash
mkdir -p ~/.agents/skills
cp -R skills/scientific-probe ~/.agents/skills/
cp -R skills/lean-scientific-computing ~/.agents/skills/
```

Codex normally detects Skill changes automatically. Restart Codex if the updated catalog does not appear.

You can also ask the built-in installer to fetch either GitHub directory:

```text
Use $skill-installer to install the skill from
https://github.com/hyh31415-maker/lean-scientific-computing/tree/main/skills/scientific-probe
```

```text
Use $skill-installer to install the skill from
https://github.com/hyh31415-maker/lean-scientific-computing/tree/main/skills/lean-scientific-computing
```

## Plugin bundle

The repository includes [`.codex-plugin/plugin.json`](.codex-plugin/plugin.json), so the two Skills can be distributed as one plugin package while retaining separate activation boundaries. Publishing or marketplace installation is a separate distribution step; local authoring still uses `.agents/skills`.

## Add repository routing

Copy the concise rules in [`templates/AGENTS.md`](templates/AGENTS.md) into a target repository’s `AGENTS.md`. The routing file is intentionally small; detailed workflows remain inside the Skills.

## Example

```text
Use $scientific-probe in DISCOVERY mode to find structurally different
explanations for the oscillation, then select the cheapest observation that
could separate the leading candidates. Freeze that one probe. Use
$lean-scientific-computing only for the implementation needed to produce the
Evidence Record, then interpret the record with $scientific-probe.
```

## Evaluation

The suite includes:

- per-Skill activation and behavior cases inside each Skill;
- cross-Skill routing cases in [`evals/routing-prompts.csv`](evals/routing-prompts.csv);
- a coordination rubric in [`evals/coordination-rubric.md`](evals/coordination-rubric.md).

The target is observable behavior: correct mode and ownership, genuinely distinct alternatives, preserved contract fields, minimal implementation, meaningful scientific checks, honest evidence labels, and deliberate stopping.

## Domain material

`lean-scientific-computing` includes focused references for project maturity, the scientific spine, verification, and ocean/BGC/Earth-observation work. These are loaded only when relevant.

## License

MIT
