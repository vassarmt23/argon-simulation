# Rahman 1964 Liquid Argon Simulation Analysis

[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Code style: Ruff](<https://img.shields.io/badge/code%20style-ruff-000000.svg>)](https://github.com/astral-sh/ruff)

> **Reproducing the foundations of molecular dynamics simulation**

A toolkit for reproducing the results from **Aneesur Rahman's 1964 paper** *"Correlations in the Motion of Atoms in Liquid Argon"* ([Physical Review 136, A405](https://doi.org/10.1103/PhysRev.136.A405)). This seminal work founded the field of molecular dynamics simulation by demonstrating its power to reveal microscopic, time-dependent behavior in liquids.

## 🔬 About Rahman's 1964 Paper

Rahman's paper was revolutionary for several reasons:

- **First molecular dynamics simulation** of a realistic liquid system (864 argon atoms)
- **Introduction of periodic boundary conditions** to simulate bulk behavior
- **Direct calculation of time-correlation functions** from atomic trajectories
- **Validation of theoretical models** through computational "experiments"
- **Discovery of complex atomic motion** including velocity "back-scattering" effects

The simulation revealed that liquid argon atoms don't undergo simple Brownian motion, but instead show complex dynamics including temporary "caging" by neighbors and subsequent escape—insights impossible to obtain from experiment alone.

## 🚀 Quick Start

### Prerequisites

- Python 3.10+
- [uv](https://docs.astral.sh/uv/) package manager

### Installation

```bash
git clone https://github.com/hunter-heidenreich/argon-simulation.git
cd argon-simulation
make install
```

### Generate Results

```bash
# Run simulation and generate all analyses
make workflow

# Generate specific analyses
make figure-2    # Radial distribution function g(r)
make figure-3    # Mean square displacement & diffusion
make figure-4    # Velocity autocorrelation function

# View all available commands
make help
```

## 📊 Analysis Features

### Core Physical Quantities

- **🌡️ Temperature Analysis** - Instantaneous temperature from kinetic energy
- **📍 Radial Distribution Function g(r)** - Atomic structure characterization
- **📏 Mean Square Displacement** - Diffusive behavior and diffusion coefficient
- **🔄 Velocity Autocorrelation Function** - Atomic motion memory effects
- **📐 Van Hove Correlation Functions** - Space-time correlation analysis

### Features

- **⚡ Intelligent Caching** - Expensive computations cached automatically
- **🧠 Memory Management** - Handles large trajectories efficiently
- **📈 Professional Plotting** - Publication-ready figures
- **🔬 Rahman Comparisons** - Direct comparison with 1964 paper values

## 🏗️ Project Structure

```
argon-sim/
├── src/argon_sim/           # Core analysis package
│   ├── trajectory.py        # LAMMPS file parsing
│   ├── thermodynamics.py    # Temperature calculations
│   ├── dynamics.py          # MSD, VACF analysis
│   ├── structure.py         # g(r), Van Hove functions
│   ├── caching.py           # Intelligent caching system
│   └── constants.py         # Physical constants
├── scripts/                 # Analysis scripts (figure_*.py)
├── artifacts/               # Generated figures and logs
├── cache/                   # Cached computation results
├── Makefile                 # Easy-to-use commands
└── pyproject.toml           # Project configuration
```

## 📄 Citation

If you use this code in your research, please cite Rahman's original paper:

```bibtex
@article{Rahman1964,
  title={Correlations in the Motion of Atoms in Liquid Argon},
  author={Rahman, Aneesur},
  journal={Physical Review},
  volume={136},
  number={2A},
  pages={A405--A411},
  year={1964},
  publisher={American Physical Society},
  doi={10.1103/PhysRev.136.A405}
}
```

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

*"The detailed microscopic behavior of a liquid is extremely complex, but computer simulation makes it possible to follow the motion of every atom."* - A. Rahman, 1964
