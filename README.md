# Structural Health Monitoring of the Hohenzollernbrücke

Detection and localisation of structural damage in the Hohenzollernbrücke (Cologne, Germany) using computational intelligence methods applied to FEA simulation data.

## Problem

Given transient structural simulation data (deformations and shear stresses at ~29,000 nodes over 11 time steps) from a finite element model of the bridge under various loading conditions:

1. **Damage Detection:** Classify whether the structure is perfect or imperfect, and if imperfect, identify which of 5 damage locations it belongs to.
2. **Damage Localisation:** Pinpoint the exact nodal region of the structural imperfection.

## Dataset

- 4 perfect structure cases and 15 imperfect structure cases (5 damage locations × 3 loading conditions)
- 1 test case with known ground truth for validation
- Each case contains 7 CSV files: directional deformations (X, Y, Z), total deformation, and shear stresses (XY, XZ, YZ)

## Project Structure
├── data/                  # Simulation data (not tracked by git)
├── notebooks/             # Jupyter notebooks for exploration and analysis
├── src/                   # Python modules (data loading, features, models)
├── docs/                  # Phase documentation (Word files)
├── models/                # Saved trained models (not tracked by git)
├── results/               # Output figures and metrics
├── requirements.txt       # Python dependencies
├── environment.yml        # Conda environment export
└── README.md

## Setup

```bash
conda create -n shm python=3.11 -y
conda activate shm
pip install -r requirements.txt
```

## Context

Originally a group project for the Computational Intelligence in Engineering course (WS 2023–24) at RWTH Aachen University, Institute of General Mechanics (IAM). Revisited as a solo learning project in 2026.