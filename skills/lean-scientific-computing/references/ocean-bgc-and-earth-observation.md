# Ocean BGC and Earth-Observation Heuristics

Read this optional reference for oceanography, aquatic biogeochemistry, remote sensing, microbial processes, organic carbon, or coupled Earth-system work. Use only relevant heuristics; they are not a mandatory project structure or stage sequence.

## Host numerics and biogeochemistry

A useful boundary reflected in MARBL and FABM is:

```text
host: grid, transport, diffusion, boundary numerics, time stepping
BGC:  local sources/sinks, transformations, exchanges, diagnostics
```

For tracer \(\chi\), the BGC core may expose local tendency \(B_\chi(x)\) while the host applies transport and integration. State ownership of air-sea, sediment, and boundary fluxes explicitly.

Do not create a generic host interface for one host. Start with a direct call or thin adapter; a BMI/FABM-style boundary is earned by a second real host or fixed external contract.

## Processes and budgets

For a new or substantially revised multi-pool model, this pattern can expose ownership:

```text
process_rates = R(state, forcing, parameters)
bgc_tendency  = S @ process_rates
```

`R` contains mechanisms such as growth, uptake, grazing, mortality, remineralization, aggregation, dissolution, sorption, sinking, or gas exchange. `S` maps them to pools through stoichiometry. This is optional: keep a direct right-hand side when clearer. Each process must remain traceable to pools, parameters, units, and diagnostics.

Expose relevant C, N, P, Si, Fe, O, charge, DIC, or alkalinity budgets. Separate internal transfers from gas exchange, burial, deposition, sediment exchange, and open-boundary fluxes. Do not apply a closed-box conservation test without accounting for external terms.

## Discriminating geometry

Use the least expensive geometry that answers the question:

```text
rate function | closed/forced box | 1D column | regional/full host
```

These are choices, not a required progression. A rate function or box isolates local processes; a spatial host is needed when mixing, transport, boundaries, or heterogeneity affect the conclusion. Higher dimension is not stronger evidence for uncertainty in a local rate law.

## Variable roles and observations

Distinguish:

- **prognostic state:** integrated pools or tracers;
- **forcing:** prescribed temperature, light, mixing, velocity, deposition, or external state;
- **diagnostic:** rates, limitation factors, production, respiration, export, residuals, and budgets;
- **observation operator:** mapping from model state to a measured proxy or product.

Do not treat remote-sensing, optical, molecular, or microbial measurements as model states unless the observation operator justifies that equivalence.

## Microbial and organic carbon

Expose definitions that affect interpretation: DOC/POC and lability classes; represented biomass or functional groups; included uptake, growth-efficiency, respiration, mortality, lysis, aggregation, sorption, and photochemical terms; fixed/flexible elemental ratios; parameterization regime and timescale; and the measured proxy for each modeled quantity.

When a user, repository, or verified source specifies a local mechanism, encode its scope in the parameter or experiment. If competing mechanisms change the conclusion, use cheap alternative experiments or report the conflict; do not select one because it is generically common.

## Earth-observation inputs

For NetCDF or Zarr, preserve labeled dimensions and relevant CF-style metadata: names, units, coordinates, vertical convention, time/calendar, flags, ranges, and grid mapping.

For remote-sensing or gridded products, expose the applicable product/level/algorithm/version, quality and cloud/ice/land treatment, spatial support and resampling, temporal compositing and missingness, uncertainty layer, coordinate system, and observation operator.

Use a small manifest for a few assets. Use a static STAC catalog when many assets need discovery; a STAC API or database requires a current serving or repeated-query need.

## Optional BGC calibration heuristics

- Verify nominal behavior, units, limits, and budgets before fitting.
- Tune only parameters informed by observations; screen sensitivity and practical identifiability before expensive joint fitting.
- Keep objective components and parameter compensation visible.
- Use held-out seasons, regions, depths, treatments, or regimes for validation claims.
- Add Bayesian, ensemble, assimilation, or PEST++ machinery only when uncertainty or inverse structure is part of the research question.

Apply only relevant items; do not force a calibration ceremony onto a local change.

Design basis: [MARBL](https://marbl.readthedocs.io/en/latest/dev-guide/introduction.html), [FABM](https://github.com/fabm-model/fabm), [OceanBioME](https://github.com/OceanBioME/OceanBioME.jl), [AIBECS](https://github.com/JuliaOcean/AIBECS.jl), [CF Conventions](https://cfconventions.org/), and [STAC](https://stacspec.org/).
