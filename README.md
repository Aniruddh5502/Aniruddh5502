# Aniruddh Biswas Badhon (Ani)

## Bridging between Physics, Intelligence, and Silicon

Hi there, I work with machines, hardware, software(firmware), simulations, data processing, surrogate model building and combining all of them in coherent processes to complete the cycle and keep it ongoing. I use tools including design tools like blender for 3D graphics, Solidworks, AutoCAD for modeling CAD, Simulations using SolidWorks, Ansys, FEA etc sectors. I also script thousands of simulations generating data, processing them and using them to train surrogate models and make predictions orders of magnitude faster. I include ML, AI where its needed as per requirements and feasability.

---

###  Core Artifacts

#### [Mechanical Design Optimization Framework](https://github.com/Aniruddh5502/mechanical-design-optimization-framework) | *Probabilistic Surrogate Modeling*
A full-stack pipeline for the parametric optimization of MEMS accelerometer flexures.
- **The Pipeline:** Scripted ANSYS simulations $\rightarrow$ Ensemble Neural Network $\rightarrow$ NSGA-II Optimization.
- **Probabilistic ROM:** Built an ensemble of 20 MLP regressors to predict 10 structural outputs (Modal Frequencies, Stress, Deformation).
- **Uncertainty Quantification:** Instead of a black-box mean, the system outputs a standard deviation ($\sigma$), enabling reliability-aware design exploration.
- **High Precision:** Achieved $R^2$ scores up to **0.9995** for critical modal frequencies.
- **Analysis:** Utilized Jacobian sensitivity analysis and UMAP manifold extraction to validate the model's latent space.

#### [Cerberus](https://github.com/Aniruddh5502/cerberus) | A Fault Tolerant Firmware Management System for ESP32 without RAD Hardened Hardware
**Background**: This project was initially built for a Startups requirement for reliable flight controller setup that will be used in their rocket. Its a local startup in Bangladesh, and the fund is not that much. And they wanted TMR logic in them as their requirement. So I studied those TMR and made one for them. But then I thought what if the firmware gets currupted?? Then there would be no meaning of having 3 modules voting, cause one will be dead already, in the fortunate case. So I thought if I could improve it, not for the startup but for my own project. I thought okay so if the firmware can check on itself if its okay and fix if some bit flip has happened then it could work. I tried to write some code that edits itself. When I ran it, I found that the binary is often locked when running. So then I thought okay I have used partitioning in ESP32 so if One partition can check all the partions binary and if it finds error in its binary it shifts control to another one, and reboots, and if any other one is currupted then it does a page wise(there are pages in binary reading and writing using ESP32s APIs) then that could work, then I tested it. And its working fine. Then I automated the total testing facility and built a demo class for showing how the operations can be done with 2 layered TMR on top of this firmware management. 

It's not a fully deployable one in flight computer. Its a design study on how to make them. If you are wondering if this repo actually flaushes and runs code or not. I must tell you it does :3

An industrial-grade firmware framework for ESP32 designed for safety-critical environments (e.g., flight controllers).
- **Autonomous Self-Healing:** Triple OTA partition management (`ota_0, 1, 2`) with SHA-256 validation every 60s. Automatically performs chunk-based (4KB) destructive copies to repair corrupted firmware slots.
- **Two-Layer TMR:** Implemented a high-order redundancy pattern for critical data and arithmetic. 
  - *Layer 1:* Majority vote across 3 rows $\rightarrow$ 3 candidates.
  - *Layer 2:* Majority vote of candidates $\rightarrow$ validated result.
- **Computational Redundancy:** Prevents transient CPU faults by executing arithmetic operations 9 times independently with `volatile` barriers to prevent compiler optimization.
- **Validation:** Rigorous test suite that systematically injects corruption into flash memory to verify autonomous recovery.


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
