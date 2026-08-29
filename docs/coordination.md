# Coordination Architecture

The two Skills form a staged research system, not two competing collections of generic “best practices.”

## Ownership

| Concern | `scientific-probe` | `lean-scientific-computing` |
|---|---|---|
| Scientific question or discovery target | Owns | Consumes |
| Candidate mechanisms or model classes | Generates and compares | Preserves |
| Discriminating prediction or discovery signal | Owns | Implements |
| Observable, statistic, branch rule, and decision rule | Owns | Preserves without silent changes |
| Experimental controls | Specifies | Implements and verifies |
| Data, equations, parameters, and solver path | Constrains only as needed | Owns |
| Project structure and dependencies | Sets a scientific ceiling only | Owns through the complexity gate |
| Raw outputs and provenance | Specifies required evidence | Produces the Evidence Record |
| Scientific interpretation | Owns | Reports observations and implementation facts |
| Repository simplification | Defines evidence that must survive | Owns |
| Product deployment | Exits after the scientific decision | Exits to normal production engineering |

## Probe modes

### DISCOVERY

Use when the hypothesis space is incomplete, observations are surprising, or the main task is to discover a useful mechanism or discriminator.

- Generate structurally different candidates, not wording variants.
- Challenge consequential soft assumptions.
- Run one cheap primary probe and, when justified, one orthogonal or adversarial probe.
- Allow adaptive branching, but log every branch and selection.
- Do not present a selected exploratory result as confirmatory evidence.

### DISCRIMINATION

Use when credible alternatives already exist and can make different predictions. Freeze the primary observable, analysis rule, decision rule, and stop rule before inspecting the result.

### REPLICATION

Use when testing an existing reported claim. Freeze the evaluated population, exclusions, preprocessing, statistic, success/failure rule, and stop rule before rerunning it. Deviations remain visible.

A Probe Contract freezes one probe. It does not prevent the wider research program from adapting through a new contract after surprising evidence.

## Routing state machine

### State A — unresolved inference or discovery

Use `scientific-probe` when the main uncertainty is scientific:

- whether an effect exists;
- which mechanism or model class explains an observation;
- whether a reported result replicates;
- what unexpected pattern deserves follow-up;
- which observation would distinguish alternatives;
- what a result justifies.

The output is a **Probe Contract** with a declared mode.

### State B — defined scientific computation

Use `lean-scientific-computing` when the scientific target is sufficiently specified and the remaining work is computational:

- implement a stated equation or parameterization;
- prepare or transform a defined dataset;
- run a specified simulation, calibration, comparison, or exploratory branch;
- add a diagnostic required by the contract;
- simplify code while preserving declared evidence.

The output is an **Evidence Record**. Each run is labeled confirmatory, exploratory, feasibility-only, or invalid.

### State C — evidence interpretation

Return the Evidence Record to `scientific-probe` when a scientific conclusion, belief update, or next probe is required. The implementation Skill must not quietly revise the question, threshold, or interpretation.

When evidence violates all current candidates or a control fails, use the surprise protocol: mark the current probe unresolved or invalid, reopen assumptions, and create a new contract. Do not patch the old metric until the result looks favorable.

### State D — promotion

Only after the effect or method is sufficiently established should a project be promoted for wider reuse or operation. Promotion requires a current obligation such as multiple real consumers, a fixed external interface, uptime, security, or compatibility commitments.

## Mixed requests

For “build an API for this new method, but first show it beats the baseline”:

1. `scientific-probe` selects the mode and defines the Probe Contract.
2. `lean-scientific-computing` produces the smallest valid Evidence Record.
3. `scientific-probe` interprets the evidence.
4. Product engineering begins only if the result and user decision justify it.

Do not design the API in parallel unless an API constraint changes the scientific test itself.

When both Skills are named in one prompt, they must not emit independent plans. Produce one Probe Contract, one implementation pass, one Evidence Record, and one interpretation.

## Contract integrity

For DISCRIMINATION and REPLICATION, implementation must not silently change:

- alternatives or claim;
- scientific population, exclusions, or sample-changing preprocessing;
- controls;
- primary observable or statistic;
- analysis and decision rule;
- seed or initialization policy when consequential;
- stop rule.

For DISCOVERY, the current probe and evidence-capture rules remain fixed, but branching may adapt. Every branch, failed attempt, changed metric, and selection criterion must be recorded and must remain exploratory.

A necessary deviation should be declared before the affected run when possible. A post-result change can generate a new hypothesis, not retroactively strengthen the original test.

## Keep contracts proportional

The handoff is not a project-management ceremony.

- A hand calculation may use a five-line contract and no repository changes.
- A C0 discovery run may use one scratch script and a compact exploration log.
- Consequential stochastic or data-dependent work needs a fuller contract.
- Do not generate a protocol document, issue backlog, or architecture plan unless the scientific or operational obligation requires it.

## Anti-loop rule

Do not bounce between Skills for local reversible details.

- A probe may execute a trivial scratch calculation directly.
- A lean implementation may resolve local coding details directly.
- Handoff only when ownership changes: inquiry design -> implementation, or evidence -> interpretation.
- If only one Skill is installed, preserve the same boundary locally rather than blocking.

## Orthogonal axes

Research phase and project maturity are different:

- **Research phase:** discovery/question -> probe -> evidence -> inference.
- **Project maturity:** C0 exploration -> C1 reproducible study -> C2 shared component -> C3 operational system.

A C0 probe can be rigorous while using a disposable script. A C2 component can implement a settled method without reopening its hypotheses. Project size and software maturity are not measures of evidence strength.
