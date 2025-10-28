
# Quantum_QCO_ConferencePaper

<div align="center">

<!-- badges: start -->
<a href="https://shields.io"><img src="https://img.shields.io/badge/status-active-brightgreen.svg" alt="status"></a>
<a href="https://shields.io"><img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="license"></a>
<a href="https://shields.io"><img src="https://img.shields.io/badge/python-3.8%2B-orange.svg" alt="python"></a>
<!-- badges: end -->

</div>

Quantum‑Cognizant Service Placement in Edge Computing Networks using Variational Quantum Algorithms explores hybrid quantum‑classical methods for mapping distributed AI services onto heterogeneous edge servers.
The work formalizes the Quantum‑Cognizant Service Placement Problem (QC‑SPP) as a multi‑objective optimization balancing latency, load, and the strategic use of scarce quantum resources.

### Overview
- Objective: minimize communication latency and server load while maximizing high‑utility quantum task placement under realistic resource constraints.
- Approach: an edge‑network simulator, quantum encodings, and hybrid solvers centered on VQE with targeted refinement.

### Key findings
- Hybrid robustness: an Adaptive Hybrid pipeline using a strong classical initializer plus VQE refinement is more resilient to simulated noise than a pure VQE baseline.
- Nuanced advantage: quantum‑hybrid methods match strong classical cost baselines while improving stability (e.g., fewer hotspots) and prioritizing high‑utility quantum tasks.
- Scalability trade‑offs: logarithmic encodings scale better than one‑hot encodings, which quickly become qubit‑ and time‑limited on larger instances.

### Project structure
- EdgeEnvironment: generates heterogeneous edge networks, including difficult uniform‑latency cases to stress greedy heuristics.
- DistributedAIModel: builds service‑DAG workloads with graded quantum utility.
- Quantum optimizers: VQEOptimizer (log encoding), NoisyVQEOptimizer (depolarizing model), and QAOAOptimizer for comparison.
- Hybrid optimizers: ImprovedIterativeHybridOptimizer for classical‑guided seeding with VQE refinement and adaptive decomposition.
- ExperimentRunner: end‑to‑end automation for scalability tests, ablations, noise studies, and algorithm comparisons.

### Prerequisites
- Python 3.8+
- PennyLane
- NumPy
- SciPy
- Matplotlib
- Seaborn
- NetworkX

### Quick start
- Clone and set up a fresh environment, then install Python dependencies as below.

```bash
git clone https://github.com/<your-org>/Quantum_QCO_ConferencePaper.git
cd Quantum_QCO_ConferencePaper
python -m venv .venv && source .venv/bin/activate  # Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

- Run the notebook QCO-v2.1.ipynb or execute the Python script variant to reproduce experiments.[1]

### Citation
If this repository helps your research, please cite: “Quantum‑Cognizant Service Placement in Edge Computing Networks using Variational Quantum Algorithms.”

