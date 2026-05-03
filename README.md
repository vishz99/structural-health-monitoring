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

## Approach

The problem is framed as a **multi-class classification task with 6 classes**: `perfect`, `imperfect_1`, `imperfect_2`, `imperfect_3`, `imperfect_4`, and `imperfect_5`. Given the structural response data (deformations and stresses across all nodes and time steps), the model predicts which class the case belongs to. A prediction of `perfect` means the structure is healthy; a prediction of `imperfect_N` means structural damage at location N.

The raw data is high-dimensional (~29,000 nodes × 11 time steps × 7 quantities per case) but the sample count is small (19 training cases).

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

Project for the Computational Intelligence in Engineering course (WS 2023–24) at RWTH Aachen University, Institute of General Mechanics (IAM). Revisited in 2026.