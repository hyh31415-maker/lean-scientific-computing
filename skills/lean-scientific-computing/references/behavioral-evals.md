# Behavioral Evaluations

Read this file only when creating, revising, or evaluating `lean-scientific-computing`. Evaluate observable decisions and artifacts, not exact wording or headings.

## Evaluation protocol

For each case, give the agent the realistic request and a small representative repository or file set. Do not tell it the expected architecture. Inspect the resulting plan, diff, commands, and handoff.

Global pass conditions:

- one direct scientific control path remains;
- every new permanent mechanism has a current requirement;
- inputs, formulas, parameters, objectives, and outputs remain traceable;
- relevant scientific checks exercise a non-empty case;
- uncertain but reversible scientific choices do not become unnecessary blockers;
- no claim exceeds the evidence actually produced;
- the agent stops without adjacent redesign.

Hard failures:

- database, service, plugin system, generic registry, workflow engine, or compatibility layer without its activation condition;
- duplicate parameter or configuration sources;
- changed scientific behavior protected only by import, lint, or generic unit tests;
- silent data repair or fallback that changes the scientific sample;
- leaving old and new execution routes active after simplification;
- suppressing needed C2/C3 architecture despite real external obligations.

## Case 1 — Local process change

**Request:** Add a Q10 temperature response to phytoplankton growth in an existing NPZD model.

Expected decisions:

- edit the owning rate equation and authoritative parameter registry;
- expose or preserve the temperature factor as a diagnostic when useful;
- check the reference temperature, one warmer point, units, and an affected budget or short box run;
- do not add a process plugin interface, model factory, or generalized environmental-response framework.

## Case 2 — One remote-sensing product

**Request:** Use one satellite chlorophyll product as a forcing or comparison dataset.

Expected decisions:

- add one catalog entry or acquisition recipe and a thin explicit adapter;
- preserve product version, quality flags, units, grid, time aggregation, and observation-operator assumptions;
- exercise a real sample;
- do not create a database, STAC API, ingestion service, or generic provider framework.

## Case 3 — New 0D prototype

**Request:** Prototype an NPZD box model to test whether grazing can generate oscillations.

Expected decisions:

- choose C0 or a compact C1 structure;
- implement explicit states, rates, parameters, a driver, and a small output;
- run a discriminating parameter case and inspect the budget;
- do not scaffold a package, CLI, documentation site, CI matrix, or host-coupling layer.

## Case 4 — Twenty tunable parameters

**Request:** Fit 20 BGC parameters against nutrients, chlorophyll, and oxygen observations.

Expected decisions:

- make the objective decomposable by dataset or variable;
- check bounds, transforms, fixed/tunable selection, and seeds;
- screen sensitivity or identifiability before expensive joint optimization;
- preserve held-out regimes;
- do not build an MLOps platform or claim one optimum uniquely identifies all parameters.

## Case 5 — One new diagnostic

**Request:** Save particulate organic carbon export and remineralization diagnostics.

Expected decisions:

- expose existing process terms from their owning equations;
- add output variables with dimensions, units, coordinates, and provenance;
- reopen and inspect the written output;
- do not add a dashboard, reporting engine, database, or duplicate equation in plotting code.

## Case 6 — Second real host model

**Request:** The same BGC core now needs to run in both a 1D column model and a regional circulation model.

Expected decisions:

- recognize that a reusable boundary is now earned;
- define the smallest state, forcing, tendency, flux, and diagnostic exchange contract;
- consider a thin BMI/FABM-style adapter rather than duplicating the core;
- avoid importing unrelated features from a full coupling framework.

## Case 7 — Large repeated ensemble

**Request:** Run 10,000 ensemble members on HPC with partial recomputation after input changes.

Expected decisions:

- recognize scheduler integration, dependencies, restartability, and partial recomputation as current requirements;
- allow an existing workflow system such as Snakemake;
- keep the scientific run command usable independently of the workflow engine;
- record experiment and parameter identities without building an unrelated service platform.

## Case 8 — Simplify overbuilt orchestration

**Request:** A small study has loaders, repositories, factories, service classes, and three configuration layers around one model run. Simplify it without changing results.

Expected decisions:

- freeze a representative result and trace the live scientific route;
- collapse single-consumer seams into their actual owners;
- preserve one parameter source and one run path;
- delete superseded code and compare scientific outputs;
- do not rewrite the model or add a replacement framework.

## Case 9 — Sparse evidence for a rate

**Request:** Implement a remineralization temperature dependence even though local evidence is sparse and literature values differ.

Expected decisions:

- use the best current working form when the user wants implementation;
- isolate the uncertainty in explicit parameters or experiment alternatives;
- record source and rationale once;
- select a discriminating sensitivity or regime comparison;
- do not block on a systematic review or repeat generic cautions.

## Case 10 — Genuine operational system

**Request:** Turn the model into a public operational forecast API with uptime, authentication, and compatibility obligations.

Expected decisions:

- identify C3 and route to normal production architecture;
- preserve the scientific core boundary while allowing service, security, monitoring, deployment, and compatibility work;
- do not misuse minimalism to remove required operational controls.

## Regression questions

After revising the skill, test at least one C0, C1, C2, and C3 case. Compare against the prior version when possible:

- Did the revision reduce an observed failure, or merely add more instructions?
- Did it improve scientific traceability without increasing project ceremony?
- Does a small task remain small?
- Can a real promotion trigger still activate mature infrastructure?

Prefer a narrow correction supported by a failed case over accumulating universal rules.
