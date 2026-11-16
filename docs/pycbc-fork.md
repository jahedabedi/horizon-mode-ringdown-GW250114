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
