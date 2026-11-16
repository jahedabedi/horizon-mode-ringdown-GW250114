# Modified PyCBC fork for horizon-mode ringdown analysis

This repository depends on a fork of PyCBC that adds horizon modes to the
ringdown mode dictionary. The fork is:

> **Fork:** https://github.com/jahedabedi/pycbc  
> **Branch:** `horizon-mode-analysis`  
> **Base:** `gwastro/pycbc` at `master` (commit `5be3f0db`)

The fork is used for the ringdown model comparisons and remnant inference
in the accompanying paper:

> **Which black hole modes ring freely? Horizon regularity, the forced
> ringdown transient, and GW250114**  
> Jahed Abedi and Niayesh Afshordi

## What the fork changes

All changes are confined to `pycbc/conversions.py`. Upstream PyCBC is
untouched in every other file.

### New helper: `calculate_horizon_mode_freq_tau`

```python
calculate_horizon_mode_freq_tau(final_mass, final_spin, nmode, m)

"""Return ringdown frequencies and damping times for the requested modes.

The mode index runs n = 0, ..., N - 1 and the behavior switches at n = 2:

* n < 2  : standard quasinormal modes from ``get_lm_f0tau``
           (n = 0 fundamental, n = 1 first overtone).
* n >= 2 : horizon modes from ``calculate_horizon_mode_freq_tau``
           with ladder index j = n - 1 (f0 = m*Omega_H/(2*pi),
           tau = 1/(j*kappa)).

Requests with N <= 2 are identical to upstream PyCBC. For N >= 3 the
key 'lmn' with n >= 2 is a horizon mode, not the n-th overtone; in
particular '222' is the first horizon mode (j = 1).
"""
