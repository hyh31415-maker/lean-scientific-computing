# Ocean BGC and Earth Observation

Read this reference for oceanography, aquatic biogeochemistry, remote sensing, microbial processes, organic carbon, or coupled Earth-system work. Apply only the relevant sections.

## Separate host numerics from biogeochemistry

Use the responsibility boundary demonstrated by MARBL and FABM:

```text
host: grid, transport, diffusion, boundary numerics, time stepping
BGC:  local sources and sinks, transformations, exchanges, diagnostics
```

For tracer state \(\chi\), the BGC component should expose the scientific right-hand side \(B_\chi(x)\) or an equivalent tendency. The host may add transport and integration. Keep air-sea, sediment, or boundary exchanges explicit about which side owns the flux and which side applies it.

Do not create a generic host interface for one host. Start with a direct call or thin adapter. Promote to a BMI/FABM-style interface only after a second real host or a fixed external coupling contract exists.

## Express processes and budgets visibly

For a new or substantially revised multi-pool model, a useful form is:

```text
process_rates = R(state, forcing, parameters)
bgc_tendency  = S @ process_rates
```

`R` contains growth, uptake, grazing, mortality, remineralization, aggregation, dissolution, adsorption, sinking, gas exchange, or other mechanisms. `S` maps those rates into tracer or pool tendencies through stoichiometry.

This is a preference, not a compulsory refactor. Keep a clear direct RHS when it is more readable in the existing model. The invariant is that a reviewer can trace each process to affected pools, parameters, units, and diagnostics.

When relevant, expose budgets for C, N, P, Si, Fe, O, charge, DIC, or alkalinity. Distinguish internal transfers from external sources, sinks, burial, gas exchange, and open-boundary fluxes. A closed-box conservation test must not be applied to a deliberately open system without accounting for those terms.

## Begin with the smallest discriminating geometry

Use a 0D or box driver to test local BGC mechanisms before debugging transport and grid behavior together. Progress only as the scientific question requires:

```text
rate function -> closed or forced box -> 1D column -> regional/full host
```

A higher-dimensional host is not stronger evidence when the uncertainty is in a local rate law. Conversely, a box model cannot validate transport-dependent conclusions; promote geometry when spatial coupling is part of the hypothesis.

## States, forcings, and diagnostics

Classify variables explicitly:

- **prognostic state**: integrated pools or tracers;
- **forcing**: temperature, irradiance, mixed-layer depth, velocity, deposition, or prescribed external state;
- **diagnostic**: process rates, limitation factors, production, respiration, export, residuals, and budgets;
- **observation operator**: transformation from model state to the measured proxy or product.

Do not treat remote-sensing products or microbial proxies as direct model states unless the observation operator justifies that equivalence.

## Microbial and organic-carbon models

Make pool definitions and transformations explicit:

- operational definition of DOC, POC, dissolved/particulate, labile/semi-labile/refractory, or molecular classes;
- microbial biomass and functional groups represented;
- substrate uptake, growth efficiency, respiration, mortality, viral lysis, aggregation, sorption, and photochemical terms included;
- elemental ratios and whether they are fixed, flexible, or diagnostic;
- timescale and environmental regime for each parameterization;
- measured proxy corresponding to each modeled quantity.

Local patterns may justify a working mechanism or regime-dependent parameter. Encode the scope of that assumption in the parameter or experiment definition; do not block the model until a universal law is available.

## Earth-observation inputs

For NetCDF or Zarr products, preserve labeled dimensions and CF-style metadata: variable names, units, latitude/longitude or projected coordinates, depth or vertical convention, time and calendar, flags, valid ranges, and grid mapping.

For remote-sensing products, make these choices visible when relevant:

- product and processing level/version;
- retrieval algorithm or band-derived quantity;
- quality flags, masks, cloud/ice/land treatment;
- native spatial support and resampling method;
- temporal compositing and missing-observation behavior;
- uncertainty or confidence layer;
- coordinate reference system;
- observation operator linking the product to the BGC state.

Use a small manifest for a few assets. Use a static STAC catalog when many spatiotemporal assets must be indexed or discovered. Add a STAC API or database only when serving or repeated remote search is a present requirement.

## Calibration sequence for BGC models

1. Check nominal behavior, units, limiting cases, and budgets.
2. Identify parameters that are actually tunable from the available observations.
3. Screen sensitivity before optimizing a large interacting parameter set.
4. Fix, aggregate, or condition weakly identifiable parameters rather than letting an optimizer choose arbitrary compensating values.
5. Fit with an explicit decomposable objective and appropriate parameter transforms.
6. Validate on held-out seasons, regions, depths, perturbations, or environmental regimes.
7. Add Bayesian, ensemble, or PEST++ machinery only when uncertainty, data assimilation, or high-dimensional inverse structure is itself part of the research result.

## Mature-project lessons to promote

- MARBL: the host computes transport and time evolution; the BGC library computes sources, sinks, exchanges, and intermediate diagnostics.
- FABM: models, drivers, configuration, and test cases are distinct; a 0D driver provides a low-cost scientific proving ground.
- OceanBioME: domain modules can coexist with a compact box-model driver rather than forcing all work through a full spatial model.
- AIBECS: start repository guidance with the governing equation and a short runnable recipe; keep parameter units, bounds, priors, optimizability, and references visible.

Do not promote their compiler matrices, language-specific metaprogramming, GPU infrastructure, plugin graphs, release machinery, or compatibility layers into a small research project.

Primary references:

- https://marbl.readthedocs.io/en/latest/dev-guide/introduction.html
- https://github.com/fabm-model/fabm
- https://github.com/OceanBioME/OceanBioME.jl
- https://github.com/JuliaOcean/AIBECS.jl
- https://cfconventions.org/
- https://stacspec.org/
