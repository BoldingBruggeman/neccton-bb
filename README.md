# NECCTON-BB

This repository contains tools to work with the [Framework for Aquatic Biogeochemical Models (FABM)](https://fabm.net) in the [NECCTON project](https://neccton.eu). Specifically, it combines:

* FABM itself
* several third-party biogeochemical models (ERSEM, PISCES, ECOSMO)
* the [General Ocean Turbulence Model (GOTM)](https://gotm.net): a 1D water column model used often to test biogeochemcial models

The code for eahc of these is included as a git submodule, located at [`extern`](extern).

## Use with Binder

You can use the software in this repository without installing anything locally:

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/BoldingBruggeman/neccton-bb/HEAD?urlpath=lab%2Ftree%2Fnotebooks)

## Installing

The software in this repository works on Linux, Windows and Mac.

We recommend installing with [Anaconda](https://www.anaconda.com/products/individual). On many systems Anaconda is already installed: try running `conda --version`. If that fails on Linux, you may need to load an anaconda module first: try `module load anaconda` or `module load anaconda3`. If that still does not give you a working `conda` command, you can install [Miniconda](https://docs.conda.io/en/latest/miniconda.html), which does not require root/administrator privileges.

Before using Anaconda for the first time, you may need to initialize it for shell interaction (this is not needed if you let the installer do this): execute `conda init`. Optionally, you can add an argument to specify which shell you will be using (default: cmd.exe/powershell on Windows, bash on Linux). This needs to be done just once. After initializing the conda environment, restart your shell by logging out and back in.

To build and install all software:

```bash
conda env create -f environment.yml
conda activate neccton-bb
bash ./install
```

### Staying up to date

To update to the latest source code, rebuild, and reinstall:

```bash
git pull
git submodule update --init --recursive
conda env update -f environment.yml
conda activate neccton-bb
bash ./install
```

## How to use

After installation, you will have:

* GOTM, compiled with FABM support and the thrid-party biogeochemcial models mentioned above. This is available as the `gotm` executable, run typically from the command line.
* The `pyfabm` python package that allows you to access FABM from Python. This can be used to run box model (0D) simulations.

The repository contains [several Jupyter notebooks](notebooks) that show how to run box model simulations and how to visualize output from GOTM.