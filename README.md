# eca-phase-transition

# Phase Transition in Topological Protection of Elementary Cellular Automata

**Devon Birch** | September 2025

## Discovery

Sharp phase transition in elementary cellular automata (ECA) at activity parameter λ ≈ 0.18, revealed through exhaustive analysis of all 256 binary rules.

### Key Findings

- **Critical transition**: λ = 0.178 ± 0.003 (Mann-Whitney p < 0.0001, >4σ effect size)
- **Below threshold**: 76.2% of rules exhibit rigid topological protection (stable domain walls)
- **Above threshold**: Protection drops to ~25%, despite preserved Z₂ parity (mean deviation 0.434)
- **Reversible rules**: Cluster at phase boundaries, acting as natural criticality probes
- **Universal bound**: Sub-luminal velocity constraint v < 1.2 across all regimes

## Phase Diagram

![Phase Diagram](figures/phase_diagram.png)

*Activity parameter λ vs velocity |v| for all 256 ECA rules. Blue: strong topological protection, Red: weak protection*

## Extension to Higher States

Analysis extended to ternary (q=3, 2187 rules) and quaternary (q=4, 10k sample) totalistic CA:
- Reveals constraint-dependent "valley" structures
- Inverted correlation (λ vs variance = -0.006) compared to binary (+0.82)
- Demonstrates how totalistic constraints bifurcate dynamics for q>2

## Repository Contents├── paper/ │   └── eca_phase_transition.pdf    # Full paper with methods and analysis ├── code/ │   ├── binary_eca_analysis.py      # All 256 binary rules │   ├── ternary_totalistic.py       # All 2187 ternary rules │   └── quaternary_sample.py        # Q=4 sampling (10k rules) ├── data/ │   ├── binary_results.npz          # Complete binary ECA results │   ├── ternary_results.npz         # Ternary totalistic results │   └── q4_sample.npz              # Quaternary sample data ├── figures/ │   ├── phase_diagram.png           # Main phase transition diagram │   ├── histogram_protection.png    # Protection vs λ histogram │   └── ternary_valley.png         # Ternary valley structure └── notebooks/ └── reproduce_analysis.ipynb    # Step-by-step reproduction## Quick Start

```python
# Load and visualize the phase transition
import numpy as np
import matplotlib.pyplot as plt

data = np.load('data/binary_results.npz')
plt.scatter(data['lambda'], data['velocity'], 
           c=data['protection'], s=1/np.sqrt(data['variance']))
plt.axvline(x=0.178, linestyle='--', label='λc = 0.178')
plt.xlabel('Activity Parameter λ')
plt.ylabel('Velocity |v|')
plt.show()Statistical SignificanceMann-Whitney U-test on variance distributions: p < 0.0001Effect size: >4σ separation between phasesCorrelation (λ, variance): +0.82 above transitionBootstrap validation: 100 iterations, std 0.003CitationDevon Birch (2025). "Phase Transition in Topological Protection of Elementary Cellular Automata"
GitHub: https://github.com/[Ordo-Umbra]/eca-phase-transitionContactDevon Birch - devon.birch801@gmail.comAcknowledgmentsAnalysis assisted by Grok (xAI). Built upon foundational work by Wolfram, Langton, and the CA community.LicenseMIT License - See LICENSE file for details

**requirements.txt** (Python dependencies):numpy>=1.20.0 scipy>=1.7.0 matplotlib>=3.3.0**.gitignore**:*.pyc pycache/ .ipynb_checkpoints/ *.DS_Store### **3. Sample Code File** (code/binary_eca_analysis.py):
```python
"""
Elementary Cellular Automata Phase Transition Analysis
Devon Birch, September 2025

Identifies topological phase transition at λ ≈ 0.18


