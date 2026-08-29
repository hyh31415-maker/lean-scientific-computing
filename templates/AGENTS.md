# Scientific workflow routing

- Treat code as experimental apparatus unless the user explicitly requests a product or operational system.
- Use `$scientific-probe` when the primary uncertainty is whether, why, which mechanism, whether a result replicates, what evidence would distinguish alternatives, what anomaly to pursue, or what conclusion the evidence supports.
- Within `$scientific-probe`, use DISCOVERY for incomplete hypothesis spaces, DISCRIMINATION for competing predictions, and REPLICATION for an existing claim.
- Use `$lean-scientific-computing` when the scientific target is already defined and the task is to implement, run, verify, or simplify researcher-controlled computation.
- For mixed work, use one sequence: Probe Contract -> lean implementation -> Evidence Record -> scientific interpretation -> optional product engineering. Do not create duplicate plans.
- In DISCRIMINATION or REPLICATION, do not silently change the alternatives, population, controls, primary statistic, analysis rule, threshold, seed policy, or stop rule.
- In DISCOVERY, adaptive branches are allowed only when logged and labeled exploratory; do not promote a selected branch to confirmatory evidence.
- Do not add frameworks, services, databases, orchestration, compatibility layers, or generic extension points unless a current scientific or operational requirement earns them.
- Preserve authoritative inputs, provenance, exact rerun commands, raw outputs, and the smallest checks that could expose a wrong scientific conclusion.
- Stop when the current scientific decision is possible or the probe is shown invalid; do not automatically productize or generalize the result.
