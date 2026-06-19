# Aniruddh Biswas Badhon (Ani)

## The Bridge between Physics, Intelligence, and Silicon

I specialize in **Physical AI**: the convergence of Mechanical Engineering, Probabilistic Machine Learning, and Fault-Tolerant Embedded Systems. My work focuses on collapsing the distance between high-fidelity physical simulations and real-time, dependable execution on the edge.

I implement **End-to-End Physical Intelligence Pipelines**: 
`High-Fidelity Sim (ANSYS)` $\rightarrow$ `Probabilistic ROM (MLP Ensembles)` $\rightarrow$ `Dependable Firmware (TMR C++/RTOS)`.

---

###  Core Artifacts

#### [Cerberus](https://github.com/Aniruddh5502/fault-tolerant-system-design-ESP32) | *Dependable Embedded Systems*
An industrial-grade firmware framework for ESP32 designed for safety-critical environments (e.g., flight controllers).
- **Autonomous Self-Healing:** Triple OTA partition management (`ota_0, 1, 2`) with SHA-256 validation every 60s. Automatically performs chunk-based (4KB) destructive copies to repair corrupted firmware slots.
- **Two-Layer TMR:** Implemented a high-order redundancy pattern for critical data and arithmetic. 
  - *Layer 1:* Majority vote across 3 rows $\rightarrow$ 3 candidates.
  - *Layer 2:* Majority vote of candidates $\rightarrow$ validated result.
- **Computational Redundancy:** Prevents transient CPU faults by executing arithmetic operations 9 times independently with `volatile` barriers to prevent compiler optimization.
- **Validation:** Rigorous test suite that systematically injects corruption into flash memory to verify autonomous recovery.

#### [Mechanical Design Optimization Framework](https://github.com/Aniruddh5502/mechanical-design-optimization-framework) | *Probabilistic Surrogate Modeling*
A full-stack pipeline for the parametric optimization of MEMS accelerometer flexures.
- **The Pipeline:** Scripted ANSYS simulations $\rightarrow$ Ensemble Neural Network $\rightarrow$ NSGA-II Optimization.
- **Probabilistic ROM:** Built an ensemble of 20 MLP regressors to predict 10 structural outputs (Modal Frequencies, Stress, Deformation).
- **Uncertainty Quantification:** Instead of a black-box mean, the system outputs a standard deviation ($\sigma$), enabling reliability-aware design exploration.
- **High Precision:** Achieved $R^2$ scores up to **0.9995** for critical modal frequencies.
- **Analysis:** Utilized Jacobian sensitivity analysis and UMAP manifold extraction to validate the model's latent space.

#### [Momobot](https://github.com/Aniruddh5502/momobot) | *Agentic AI Orchestration*
A local-first AI agent built on LangGraph and Ollama, designed for autonomous engineering workflows.
- **Semantic Compaction:** Implemented a token-triggered compaction system that summarizes older conversation history into a rolling state, preventing context window saturation.
- **Complex Tooling:** Integrated a persistent shell process (`pwsh`), surgical `str_replace` for file editing, and a subagent spawning system for parallel task execution.
- **Multi-Modal:** Integrated vision-based OCR and PDF parsing (LlamaCloud) for high-density document processing.

---

###  Technical Arsenal

| Domain | Technologies |
| :--- | :--- |
| **Physical Intelligence** | Surrogate Modeling (ROMs), Probabilistic Optimization, FEA (ANSYS), CFD, SDOF Dynamics |
| **Embedded Systems** | C/C++, ESP32, TMR, OTA Management, RTOS, Hardware Watchdogs, NASA/JPL Safety Standards |
| **AI & Software** | Python, PyTorch, LangGraph, MLP Ensembles, UMAP/PCA, NumPy, Pandas |
| **Tools & Design** | SolidWorks, MATLAB, LaTeX, Blender, Playwright (Automation) |

---

###  Current Trajectory
I am currently refining the deployment of **Physics-Informed Neural Networks (PINNs)** and **Reduced Order Models (ROMs)** into hard real-time C++ environments. My goal is to eliminate the "Simulation Bottleneck" by enabling complex physics-based predictions to run in $<1\text{ms}$ on edge hardware.

[Portfolio](https://aniruddh5502.github.io/Portfolio/) | [LinkedIn](https://www.linkedin.com/in/aniruddh2122/)
