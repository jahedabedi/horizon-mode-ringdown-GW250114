# Which black hole modes ring freely? Horizon regularity, the forced ringdown transient, and GW250114

Code, configuration files, modified PyCBC environment, and posterior samples for horizon-mode and ringdown tests of **GW250114**. This repository supports the reproducible analysis pipeline and model comparisons presented in the accompanying paper:

> **Which black hole modes ring freely? Horizon regularity, the forced ringdown transient, and GW250114**  
> Jahed Abedi and Niayesh Afshordi  
> arXiv:XXXX.XXXXX [gr-qc]

The analysis tests ringdown models built from the fundamental quasinormal mode, the first overtone, and the first horizon mode, and performs remnant mass/spin inference with free mass and spin parameters.

---

## Repository contents

| Path | Description |
| :--- | :--- |
| `configs/` | Configuration files for the ringdown model fits and parameter-estimation runs. |
| `scripts/` | Python analysis scripts used to generate waveforms, run model selection, and produce posterior samples. |
| `notebooks/` | Optional notebooks for producing figures and summary tables from the posterior samples. |
| `environment/` | Instructions and files for reconstructing the modified PyCBC conda environment. |
| `data/` | Small metadata files and links to the archived posterior samples (large files are hosted on Zenodo). |
| `README.md` | This file. |
| `LICENSE` | License for the code in this repository (GPLv3; see below). |

The two main analysis directories from the cluster are:

- `220_221_FreeMassSpin_nMf/` — fundamental-mode and overtone fits with free mass and spin.
- `220_221hm_FreeMassSpin_nMf/` — fundamental-mode and first-horizon-mode fits with free mass and spin.

Their configuration files and Python codes are included here. The full posterior samples (approximately 11 GB) are archived on Zenodo; see **Data availability** below.

---

## Installation and environment

The analysis uses a **modified version of PyCBC**. The exact conda environment and PyCBC installation used for the paper are archived with the posterior samples on Zenodo.

### Option 1: Reconstruct the conda environment

```bash
conda create -n horizonmode python=3.9
conda activate horizonmode
pip install lalsuite pycbc
