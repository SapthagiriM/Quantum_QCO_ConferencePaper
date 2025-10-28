# Quantum_QCO_ConferencePaper
This repository contains the source code and experimental framework for the research paper, "Quantum-Cognizant Service Placement in Edge Computing Networks using Variational Quantum Algorithms." The project investigates the use of hybrid quantum-classical algorithms to solve the complex combinatorial optimization problem of placing distributed AI services onto a heterogeneous network of classical and quantum-enabled edge servers.
The core contribution is the formalization and solution of the Quantum-Cognizant Service Placement Problem (QC-SPP): a multi-objective optimization task that aims to minimize communication latency and server load while maximizing the strategic utilization of scarce quantum computing resources.
Key Research Findings
Our extensive simulations demonstrate several key insights into the practical application of near-term quantum algorithms:
Hybrid Algorithms Show Superior Robustness: Our novel Adaptive Hybrid algorithm, which uses a classical heuristic to find an initial solution and a Variational Quantum Eigensolver (VQE) for targeted refinement, is significantly more resilient to simulated hardware noise than a pure VQE approach.
Quantum Advantage is Nuanced: While our quantum-hybrid methods did not show a statistically significant improvement in the primary cost objective over a strong, quantum-aware classical baseline, they demonstrated clear advantages in achieving system stability (e.g., preventing server hotspots) and maximizing the placement of high-utility quantum tasks on quantum processors.
Scalability is a Critical Hurdle: The resource requirements of different quantum algorithms vary dramatically. Our results show that VQE with a logarithmic encoding is far more scalable than QAOA with a one-hot encoding, which becomes infeasible even for moderately sized problems.


Project Structure
The entire simulation is contained within a single, self-contained Jupyter Notebook (QCO-v2.1.ipynb) or Python script. The main components are:
EdgeEnvironment: A class to procedurally generate heterogeneous edge networks with a mix of classical and quantum servers. It can create "hard" problem instances with uniform network latencies to challenge greedy algorithms.
DistributedAIModel: A class to generate distributed AI applications as Directed Acyclic Graphs (DAGs), where each service has a graded "quantum utility" score.
Quantum Optimizers:
VQEOptimizer: The core VQE-based solver using a resource-efficient logarithmic encoding.
NoisyVQEOptimizer: A subclass that introduces a depolarizing noise model to simulate NISQ hardware.
QAOAOptimizer: An implementation of the Quantum Approximate Optimization Algorithm for comparison.
Hybrid Optimizers:
ImprovedIterativeHybridOptimizer: The primary novel algorithm, which combines a powerful classical greedy placement with targeted VQE refinement and adaptive problem decomposition.
ExperimentRunner: The main driver class that orchestrates all experiments, including the main scalability tests, ablation studies, noise resilience analysis, and algorithm comparisons.
Getting Started
Prerequisites
The simulation is built using Python and the PennyLane library for quantum machine learning.
Python (3.8+)
PennyLane
NumPy
SciPy
Matplotlib
Seaborn
NetworkX
