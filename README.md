The above file contains 113 rows and 108 columns. These are the converged systems in the inference sample. 

The attributes are : 
                'source_id1', 'source_id2', 
                'ra_mcmc', 'ra_err_plus', 'ra_err_minus', 'ra_gaia', 'ra_gaia_err', 
                'dec_mcmc', 'dec_err_plus', 'dec_err_minus', 'dec_gaia', 'dec_gaia_err', 
                'plx_mcmc', 'plx_err_plus', 'plx_err_minus', 'plx_gaia', 'plx_gaia_err', 
                'pmra_mcmc', 'pmra_err_plus', 'pmra_err_minus', 'pmra_gaia', 'pmra_gaia_err', 
                'pmdec_mcmc', 'pmdec_err_plus', 'pmdec_err_minus', 'pmdec_gaia', 'pmdec_gaia_err', 
                'P_days_mcmc', 'P_days_err_plus', 'P_days_err_minus', 'P_days_gaia', 'P_days_gaia_err', 
                'e_mcmc', 'e_err_plus', 'e_err_minus', 'e_gaia', 'e_gaia_err', 
                'T0_mcmc', 'T0_err_plus', 'T0_err_minus', 'T0_gaia', 'T0_gaia_err', 
                'gamma_kms_mcmc', 'gamma_kms_err_plus', 'gamma_kms_err_minus', 'gamma_kms_gaia', 'gamma_kms_gaia_err', 
                'i_deg_mcmc', 'i_deg_err_plus', 'i_deg_err_minus', 
                'Omega_deg_mcmc', 'Omega_deg_err_plus', 'Omega_deg_err_minus', 
                'omega_deg_mcmc', 'omega_deg_err_plus', 'omega_deg_err_minus', 
                'M1_mcmc', 'M1_err_plus', 'M1_err_minus', 'M1_cat', 'M1_cat_err_plus', 'M1_cat_err_minus',
                'M2_mcmc', 'M2_err_plus', 'M2_err_minus',
                'a0_mas_mcmc', 'a0_mas_err_plus', 'a0_mas_err_minus', 
                'a1_AU_mcmc', 'a1_AU_err_plus', 'a1_AU_err_minus', 
                'K1_kms_mcmc', 'K1_kms_err_plus', 'K1_kms_err_minus', 
                'q_M2overM1_mcmc', 'q_M2overM1_err_plus', 'q_M2overM1_err_minus', 
                'A_mas_gaia', 'A_mas_gaia_err', 
                'B_mas_gaia', 'B_mas_gaia_err', 
                'F_mas_gaia', 'F_mas_gaia_err', 
                'G_mas_gaia', 'G_mas_gaia_err', 
                'C_AU_gaia', 'C_AU_gaia_err', 
                'H_AU_gaia', 'H_AU_gaia_err', 
                'mcmc_total_steps', 'mcmc_gamma0', 'mcmc_acceptance_fraction', 'mcmc_tau_max', 'mcmc_chain_over_tau', 
                'convergence_status',
                'phot_g_mean_flux1', 'phot_g_mean_mag1', 'bp_rp1', 
                'phot_g_mean_flux2', 'phot_g_mean_mag2', 'bp_rp2',
                'ra2', 'dec2', 'pmra2', 'pmdec2', 'parallax2', 'pairdistance', 'sep_AU'

# Converged binary systems : Inference Sample

This table holds the **113 converged systems** from the MCMC orbit-fitting
inference sample: AstroSpectroSB1 binaries for which the fit
passed the convergence criteria (see `convergence_status` below), together
with the corresponding Gaia catalog values for comparison.

**Shape:** 113 rows × 108 columns.

**Column-naming convention** used throughout:

| Suffix | Meaning |
|---|---|
| `_mcmc` | Posterior median (or best-fit) value from this work's MCMC orbit fit |
| `_err_plus` / `_err_minus` | Asymmetric 1-sigma upper / lower uncertainty on the preceding `_mcmc` (or `_cat`) value, i.e. the 84th/16th-percentile offsets from the median |
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
AstroSpectroSB1 solution. `i_deg`, `Omega_deg`, `omega_deg` are
fitted only (As, Gaia-catalog don't provide there values).

| Column | Units | Description |
|---|---|---|
| `P_days_mcmc`, `P_days_err_plus`, `P_days_err_minus` | days | Orbital period, MCMC fit |
| `P_days_gaia`, `P_days_gaia_err` | days | Orbital period, Gaia catalog |
| `e_mcmc`, `e_err_plus`, `e_err_minus` | — | Orbital eccentricity, MCMC fit |
| `e_gaia`, `e_gaia_err` | — | Orbital eccentricity, Gaia catalog |
| `T0_mcmc`, `T0_err_plus`, `T0_err_minus` |days | Epoch of periastron passage, MCMC fit |
| `T0_gaia`, `T0_gaia_err` | days | Epoch of periastron passage, Gaia catalog |
| `gamma_kms_mcmc`, `gamma_kms_err_plus`, `gamma_kms_err_minus` | km/s | Systemic (center-of-mass) radial velocity, MCMC fit |
| `gamma_kms_gaia`, `gamma_kms_gaia_err` | km/s | Systemic radial velocity, Gaia catalog |
| `i_deg_mcmc`, `i_deg_err_plus`, `i_deg_err_minus` | deg | Orbital inclination, MCMC fit |
| `Omega_deg_mcmc`, `Omega_deg_err_plus`, `Omega_deg_err_minus` | deg | Longitude of the ascending node, MCMC fit |
| `omega_deg_mcmc`, `omega_deg_err_plus`, `omega_deg_err_minus` | deg | Argument of periastron, MCMC fit |

## 4. Masses and derived physical parameters

| Column | Units | Description |
|---|---|---|
| `M1_mcmc`, `M1_err_plus`, `M1_err_minus` | $M_\odot$ | Mass of the primary, from the dynamical MCMC fit |
| `M1_cat`, `M1_cat_err_plus`, `M1_cat_err_minus` | $M_\odot$ | Mass of the primary from an external catalog/prior (e.g. isochrone or spectroscopic mass) **[confirm source catalog]**, used for comparison with `M1_mcmc` |
| `M2_mcmc`, `M2_err_plus`, `M2_err_minus` | $M_\odot$ | Mass of the (unseen/secondary) companion, derived from the MCMC orbit fit |
| `a0_mas_mcmc`, `a0_mas_err_plus`, `a0_mas_err_minus` | mas | Photocenter semi-major axis of the astrometric orbit |
| `a1_AU_mcmc`, `a1_AU_err_plus`, `a1_AU_err_minus` | AU | Semi-major axis of the primary's orbit about the system's center of mass |
| `K1_kms_mcmc`, `K1_kms_err_plus`, `K1_kms_err_minus` | km/s | Radial-velocity semi-amplitude of the primary |
| `q_M2overM1_mcmc`, `q_M2overM1_err_plus`, `q_M2overM1_err_minus` | — | Mass ratio, $q = M_2/M_1$ |

## 5. Gaia Thiele–Innes constants

Thiele–Innes elements as published by Gaia for the combined
astrometric+spectroscopic (astrometric binary + SB1) orbital solution;
`A, B, F, G` describe the astrometric ellipse, `C, H` the spectroscopic
(radial-velocity) part of the same solution.

| Column | Units | Description |
|---|---|---|
| `A_mas_gaia`, `A_mas_gaia_err` | mas | Thiele–Innes constant $A$ |
| `B_mas_gaia`, `B_mas_gaia_err` | mas | Thiele–Innes constant $B$ |
| `F_mas_gaia`, `F_mas_gaia_err` | mas | Thiele–Innes constant $F$ |
| `G_mas_gaia`, `G_mas_gaia_err` | mas | Thiele–Innes constant $G$ |
| `C_AU_gaia`, `C_AU_gaia_err` | AU | Thiele–Innes constant $C$ (spectroscopic component) |
| `H_AU_gaia`, `H_AU_gaia_err` | AU | Thiele–Innes constant $H$ (spectroscopic component) |

## 6. MCMC fit diagnostics

Convergence/quality diagnostics for the MCMC run itself (e.g. an
`emcee`-style sampler), not physical parameters of the binary.

| Column | Description |
|---|---|
| `mcmc_total_steps` | Total number of steps run per walker in the chain |
| `mcmc_gamma0` | **[confirm]** — initial/seed value used for the systemic velocity $\gamma$ before fitting? |
| `mcmc_acceptance_fraction` | Mean acceptance fraction of the sampler across walkers (diagnostic for step-size tuning; typically healthy in the range ~0.2–0.5) |
| `mcmc_tau_max` | Largest integrated autocorrelation time among all fitted parameters, in steps |
| `mcmc_chain_over_tau` | Ratio of the chain length to `mcmc_tau_max`, used as the convergence criterion (e.g. requiring this to exceed ~50) |
| `convergence_status` | **[confirm exact values/encoding, e.g. `"converged"`/`"not converged"` string vs. 0/1 flag]** — whether the chain satisfied the convergence criterion; only converged systems (this table) pass |

## 7. Photometry

Gaia photometry for each component of the pair.

| Column | Units | Description |
|---|---|---|
| `phot_g_mean_flux1` | e-/s (Gaia internal flux units) | Mean G-band flux, component 1 |
| `phot_g_mean_mag1` | mag | Mean G-band magnitude, component 1 |
| `bp_rp1` | mag | $G_{BP}-G_{RP}$ color, component 1 |
| `phot_g_mean_flux2` | e-/s | Mean G-band flux, component 2 |
| `phot_g_mean_mag2` | mag | Mean G-band magnitude, component 2 |
| `bp_rp2` | mag | $G_{BP}-G_{RP}$ color, component 2 |

## 8. Companion (component 2) astrometry, and pair separation

Gaia astrometry for the wide companion (`source_id2`) — this component does
not have its own orbital solution in this table, only its direct Gaia
catalog values — plus the on-sky/physical separation of the pair.

| Column | Units | Description |
|---|---|---|
| `ra2` | deg | Right ascension, component 2, from Gaia |
| `dec2` | deg | Declination, component 2, from Gaia |
| `pmra2` | mas/yr | Proper motion in RA, component 2, from Gaia |
| `pmdec2` | mas/yr | Proper motion in Dec, component 2, from Gaia |
| `parallax2` | mas | Parallax, component 2, from Gaia |
| `pairdistance` | **[confirm units — arcsec/deg/mas?]** | On-sky angular separation between component 1 and component 2 |
| `sep_AU` | AU | Projected physical separation between the two components, computed from `pairdistance` and the system parallax |

---

### Open items to confirm before finalizing

- `T0_mcmc` / `T0_gaia`: exact time system and reference (BJD_TDB? JD? Gaia reference epoch offset in days?).
- `M1_cat`: which external catalog/method this mass comes from.
- `mcmc_gamma0`: confirm what this stores (initial guess vs. some other quantity).
- `convergence_status`: confirm the exact encoding of values in this column.
- `pairdistance`: confirm units (and whether it's the quantity `sep_AU` is derived from).

