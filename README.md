# Aniruddh Biswas Badhon (Ani)

## Bridging between Physics, Intelligence, and Silicon

I love to work with Machines including software and hardware. My prior education is in Mechanical Engineering from BUET and I love to work with data-finding trends, analysis and empirical descision makings from data and exploring new things. Mainly work with simulation softwares and use code to scale up processes and getting data driven descisions is my work.

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

Momobot is my daily driver for works that can be automated, done in volume or personal agentic tasks for I do not use Claude Code, Hermes, Pi or other agentic harnesses. My main motivation to use my own tools is that I know all the crux and pitfalls of them before anything has even started. When using Momobot I can print out things that its writing, running commands, searching queries all of them, even what the Orchastrator is giving to the subagents all are verifiable by me. Also there are Harness Driven test systems to check coding task completion by task state tools. That works as a hallucination proof architecture choice I made on the way. Momobot is a long project that I have been using and improving from my user experience since the start of 2025. So all the improvements tweaks are based of my experience with thsi tool for my tasks that include Mechanical Engineering, Simulation Automations, papers data checking from actual reports that are code written, writing small verifiable scripts debugging them, feature implementations and all sorts of things.
It runs on Ollama/Openrouter depending on what you set in env variables, selected models in them. It has session persistance in repo specific so all the sessions in some project folder will occur when you are in that folder. It has compaction built inside the Agentic loop so long sessions can be operated with minimal loss of information from session to session.
For Ollama specific it has Cache optimizations builtin which saves you from cold starts, KV Cache storage and in general (both Ollama and Openrouter) very high cache hit rates making it more efficient.
Tools are also made to be very context efficient designs and giving the agent much control over them to work with.
For subagent orchastration it has session persistance for the subagents, so a subagent can be reused by the main agent multiple rounds without any loss in their context.
It's still uncder development as I constantly update things to my likings and problems I face.

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

[Portfolio](https://aniruddh5502.github.io/) | [LinkedIn](https://www.linkedin.com/in/aniruddh2122/)
