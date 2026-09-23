# Data release

This repository accompanies the paper [*Companion masses of Gaia DR3 AstroSpectroSB1 binaries: a Bayesian forward-modelling framework*](https://arxiv.org/abs/2609.24321). The paper presents a Bayesian framework for inferring the masses of faint, unresolved companions by jointly modelling Gaia DR3 astrometric and spectroscopic orbital measurements using the full published covariance matrix. The method is applied to 1,035 AstroSpectroSB1 systems, including a validation sample of 760 binaries and an inference sample of 275 systems. Meaningful companion-mass estimates are obtained for 113 systems with well-converged posterior distributions.

The accompanying FITS file contains the final catalogue of 113 inferred companion masses and corresponds to the data presented in 2609.24321 [astro-ph.SR].


# Converged binary systems : Inference Sample

This FITS file holds the **113 converged systems** from the MCMC orbit-fitting
inference sample: AstroSpectroSB1 binaries for which the fit
passed the convergence criteria (see `convergence_status` below), together
with the corresponding Gaia catalog values for comparison.

**Shape:** 113 rows × 108 columns.

**Column-naming convention** used throughout:

| Suffix | Meaning |
|---|---|
| `_mcmc` | Posterior median (or best-fit) value from this work's MCMC orbit fit |
| `_err_plus` / `_err_minus` | Asymmetric 1-sigma upper / lower uncertainty on the preceding `_mcmc` value, i.e. the 84th/16th-percentile offsets from the median |
| _cat_err_plus / _cat_err_minus | Offsets of the catalogue upper/lower confidence bounds from the catalogue value |
| `_gaia` | The corresponding value as published in the Gaia catalog, for comparison with the `_mcmc` fit |
| `_gaia_err` | Symmetric 1-sigma uncertainty on the `_gaia` value |
| `1` / `2` (no underscore) | Refers to component 1 (the star with the orbital solution, `source_id1`) or component 2 (the wide companion, `source_id2`) |

---

## 1. Identifiers

| Column | Description |
|---|---|
| `source_id1` | Gaia source ID of the primary/solved component (the star with the AstroSpectroSB1 solution) |
| `source_id2` | Gaia source ID of the wide companion (component 2) |

## 2. Astrometry — position, parallax, proper motion

Fitted (`_mcmc`) vs. Gaia-catalog (`_gaia`) values for the primary component's
five astrometric parameters, each with its uncertainty.

| Column | Units | Description |
|---|---|---|
| `ra_mcmc`, `ra_err_plus`, `ra_err_minus` | deg | Right ascension from the MCMC fit, with asymmetric uncertainty |
| `ra_gaia`, `ra_gaia_err` | deg | Right ascension from the Gaia catalog |
| `dec_mcmc`, `dec_err_plus`, `dec_err_minus` | deg | Declination from the MCMC fit |
| `dec_gaia`, `dec_gaia_err` | deg | Declination from the Gaia catalog |
| `plx_mcmc`, `plx_err_plus`, `plx_err_minus` | mas | Parallax from the MCMC fit |
| `plx_gaia`, `plx_gaia_err` | mas | Parallax from the Gaia catalog |
| `pmra_mcmc`, `pmra_err_plus`, `pmra_err_minus` | mas/yr | Proper motion in RA (`pmra* cos(dec)`) from the MCMC fit |
| `pmra_gaia`, `pmra_gaia_err` | mas/yr | Proper motion in RA from the Gaia catalog |
| `pmdec_mcmc`, `pmdec_err_plus`, `pmdec_err_minus` | mas/yr | Proper motion in Dec from the MCMC fit |
| `pmdec_gaia`, `pmdec_gaia_err` | mas/yr | Proper motion in Dec from the Gaia catalog |

## 3. Orbital elements

Fitted (`_mcmc`) vs. Gaia-catalog (`_gaia`) orbital elements of the
AstroSpectroSB1 solution. `i_deg`, `Omega_deg`, and `omega_deg` are fitted only: Gaia does not publish these angles directly for AstroSpectroSB1 solutions, they are encoded implicitly in the Thiele-Innes constants

| Column | Units | Description |
|---|---|---|
| `P_days_mcmc`, `P_days_err_plus`, `P_days_err_minus` | days | Orbital period, MCMC fit |
| `P_days_gaia`, `P_days_gaia_err` | days | Orbital period, Gaia catalog |
| `e_mcmc`, `e_err_plus`, `e_err_minus` | — | Orbital eccentricity, MCMC fit |
| `e_gaia`, `e_gaia_err` | — | Orbital eccentricity, Gaia catalog |
| `T0_mcmc`, `T0_err_plus`, `T0_err_minus` |days | Epoch of periastron passage, MCMC fit |
| `T0_gaia`, `T0_gaia_err` | days | Epoch of periastron passage, Gaia catalog, it is given in days relative to the DR3 reference epoch J2016.0 (JD 2457389.0 TCB) |
| `gamma_kms_mcmc`, `gamma_kms_err_plus`, `gamma_kms_err_minus` | km/s | Systemic (center-of-mass) radial velocity, MCMC fit |
| `gamma_kms_gaia`, `gamma_kms_gaia_err` | km/s | Systemic radial velocity, Gaia catalog |
| `i_deg_mcmc`, `i_deg_err_plus`, `i_deg_err_minus` | deg | Orbital inclination, MCMC fit |
| `Omega_deg_mcmc`, `Omega_deg_err_plus`, `Omega_deg_err_minus` | deg | Longitude of the ascending node, MCMC fit |
| `omega_deg_mcmc`, `omega_deg_err_plus`, `omega_deg_err_minus` | deg | Argument of periastron, MCMC fit |

## 4. Masses and derived physical parameters

| Column | Units | Description |
|---|---|---|
| `M1_mcmc`, `M1_err_plus`, `M1_err_minus` | $M_\odot$ | Mass of the primary, from the dynamical MCMC fit |
| `M1_cat`, `M1_cat_err_plus`, `M1_cat_err_minus` | $M_\odot$ | Mass of the primary from the Gaia DR3 $\texttt{astrophysical-parameters}$ table |
| `M2_mcmc`, `M2_err_plus`, `M2_err_minus` | $M_\odot$ | Mass of the (unseen/secondary) companion, derived from the MCMC orbit fit |
| `a0_mas_mcmc`, `a0_mas_err_plus`, `a0_mas_err_minus` | mas | Photocenter semi-major axis of the astrometric orbit |
| `a1_AU_mcmc`, `a1_AU_err_plus`, `a1_AU_err_minus` | AU | Semi-major axis of the primary's orbit about the system's center of mass |
| `K1_kms_mcmc`, `K1_kms_err_plus`, `K1_kms_err_minus` | km/s | Radial-velocity semi-amplitude of the primary |
| `q_M2overM1_mcmc`, `q_M2overM1_err_plus`, `q_M2overM1_err_minus` | — | Mass ratio, $q = M_2/M_1$ |

## 5. Gaia Thiele-Innes constants

Thiele-Innes constants as published by Gaia in the $\texttt{nss-two-body-orbit}$ table for the AstroSpectroSB1 orbital solution;
`A, B, F, G` describe the astrometric ellipse, `C, H` the spectroscopic
(radial-velocity) part of the same solution.

| Column | Units | Description |
|---|---|---|
| `A_mas_gaia`, `A_mas_gaia_err` | mas | Thiele-Innes constant $A$ |
| `B_mas_gaia`, `B_mas_gaia_err` | mas | Thiele-Innes constant $B$ |
| `F_mas_gaia`, `F_mas_gaia_err` | mas | Thiele-Innes constant $F$ |
| `G_mas_gaia`, `G_mas_gaia_err` | mas | Thiele-Innes constant $G$ |
| `C_AU_gaia`, `C_AU_gaia_err` | AU | Thiele-Innes constant $C$ (spectroscopic component) |
| `H_AU_gaia`, `H_AU_gaia_err` | AU | Thiele-Innes constant $H$ (spectroscopic component) |

## 6. MCMC fit diagnostics

Convergence & quality diagnostics for the MCMC run itself, not physical parameters of the binary.

| Column | Description |
|---|---|
| `mcmc_total_steps` | Total number of steps run per walker in the chain |
| `mcmc_gamma0` | Final tuned value of the differential-evolution step-scale parameter $\gamma_0$ of the `emcee` `DEMove` sampler |
| `mcmc_acceptance_fraction` | Mean acceptance fraction of the sampler across walkers (diagnostic for step-size tuning; typically healthy in the range ~0.2–0.5) |
| `mcmc_tau_max` | Largest integrated autocorrelation time among all fitted parameters, in steps |
| `mcmc_chain_over_tau` | Ratio of the chain length to `mcmc_tau_max`, used as the convergence criterion (requiring this to exceed 50) |
| `convergence_status` | A boolean flag indicating whether the system satisfied the convergence criterion or not; only converged systems are present in above file. |

## 7. Photometry

Gaia photometry for each component of the pair.

| Column | Units | Description |
|---|---|---|
| `phot_g_mean_flux1` | electron/sec | Mean G-band flux, component 1 |
| `phot_g_mean_mag1` | mag | Mean G-band magnitude, component 1 |
| `bp_rp1` | mag | $BP - RP$ color, component 1 |
| `phot_g_mean_flux2` | electron/sec | Mean G-band flux, component 2 |
| `phot_g_mean_mag2` | mag | Mean G-band magnitude, component 2 |
| `bp_rp2` | mag | $BP - RP$ color, component 2 |

## 8. Companion (component 2) astrometry, and pair separation

Gaia astrometry for the wide companion (`source_id2`), these values come from the Wide Binary Catalog we constructed using Gaia DR3 data.

| Column | Units | Description |
|---|---|---|
| `ra2` | deg | Right ascension of component 2 |
| `dec2` | deg | Declination of component 2 |
| `pmra2` | mas/yr | Proper motion in RA of component 2 |
| `pmdec2` | mas/yr | Proper motion in Dec of component 2 |
| `parallax2` | mas | Parallax of component 2 |
| `pairdistance` | deg | On-sky angular separation between component 1 and component 2 |
| `sep_AU` | AU | Projected physical separation between the two components, computed from `pairdistance` and the parallax of component 1 |

---

## References

- Gaia DR3 `nss_two_body_orbit` table (orbital solutions, Thiele-Innes constants):
  <https://gaia.aip.de/metadata/gaiadr3/nss_two_body_orbit/>
- Gaia DR3 `gaia_source` table (astrometry, photometry):
  <https://gaia.aip.de/metadata/gaiadr3/gaia_source/>


