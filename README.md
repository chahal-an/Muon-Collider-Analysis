# Muon Collider Reconstruction Analysis

Computational physics project analyzing muon reconstruction efficiency and jet clustering in a simulated high-energy muon collider environment. Built as part of detector R&D for the muon collider physics program.

---

## Problem

High-transverse-momentum muons (>500 GeV) fail reconstruction in dense hadronic backgrounds at muon colliders. This project investigates *why* — and builds the tools to classify, visualize, and mitigate reconstruction failure.

---

## What This Project Does

- Computes muon reconstruction efficiency vs generator-level pT using ΔR-based gen-reco matching on NanoAOD ROOT files
- Visualizes particle flow (PF) candidates in η-φ space around generator muons
- Implements and extends the anti-kT jet clustering algorithm in three ways:
  - **Adaptive radius** — dynamically adjusts R based on local particle density
  - **ML-scored filtering** — scores and filters PF candidates before clustering
  - **Graph-based isolation** — uses network connectivity to separate signal from background
- Builds a 12-feature ML classification pipeline to distinguish passing from failing muons

---

## Key Results

- Identified high PF candidate multiplicity (>60 candidates in cone) as primary driver of reconstruction failure at pT > 1000 GeV
- Graph-based clustering reduced constituent count from 63 → 2 for a 1152 GeV failing muon
- 12-feature pipeline encodes spatial, density, and compositional information transferable to any point-cloud classification problem

---

## Tech Stack

| Tool | Purpose |
|------|---------|
| Python | Core analysis |
| uproot | Reading NanoAOD ROOT files |
| awkward-array | Jagged array handling |
| FastJet | Anti-kT jet clustering |
| NumPy / Matplotlib | Computation and visualization |

---

## Repository Structure

```
Muon-Collider-Analysis/
│
├── comp_physics.ipynb        # Python notebook
├── requirements.txt         # Dependencies
└── README.md
```

## Requirements

```bash
pip install uproot awkward numpy matplotlib fastjet
```

---

## Background

This work was conducted as part of graduate research in the High Energy Physics group at Northeastern University under Prof. Johan Bonilla-Castro, contributing to muon collider detector R&D. The graph-based isolation approach developed here is the algorithmic foundation for GNN-based reconstruction — currently the state of the art in collider physics and astronomical source finding.

---

## Author

**Anmoldeep Chahal (Anmol)** — MS Physics, Northeastern University  
[LinkedIn]((https://www.linkedin.com/in/contact-anmol-chahal/) |
