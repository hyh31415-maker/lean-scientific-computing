# Audit Checklist for Overengineered Research Code

## Find the scientific dependency chain

1. Identify the exact reported result, figure, table, statistic, or claim.
2. Trace backward to the code that computes it.
3. Trace backward again to the data, parameters, and assumptions it consumes.
4. Mark everything outside this path for classification, not immediate deletion.

## Classify components

- `EPISTEMIC CORE`: changing it can change the scientific conclusion.
- `REPRODUCIBILITY SUPPORT`: needed to reproduce or inspect the conclusion.
- `ENGINEERING OVERHEAD`: deployment, generic extensibility, presentation, or hypothetical reuse.
- `UNKNOWN`: insufficient evidence; inspect before changing.

## Common deletion candidates

These are candidates, not automatic deletions:

- single-implementation interfaces and abstract factories;
- registries with one entry;
- configuration inheritance for one experiment;
- wrappers that merely rename a library call;
- unused backends, adapters, serializers, and command groups;
- dashboards or APIs that duplicate a result file;
- caching or parallelism that does not make the experiment feasible;
- tests of plumbing that do not protect an invariant or inference;
- packaging and deployment files for an exploratory repository.

## Preserve despite apparent complexity

Do not remove a component merely because it is verbose when it protects:

- data provenance;
- raw result preservation;
- randomization or blinding;
- exact environment reconstruction;
- unit conversion or dimensional checks;
- numerical stability required for the claim;
- controls that distinguish apparatus failure from a null result.

## Minimal verification after simplification

- Re-run the smallest representative experiment.
- Compare the primary statistic to the previous result within a declared tolerance.
- Confirm raw outputs and provenance are still retained.
- Confirm the exact rerun command remains available.
- Confirm no hypothesis, data subset, or decision threshold changed silently.
