# Aniruddh Biswas Badhon (Ani)

## Bridging between Physics, Intelligence, and Silicon

I love to work with Machines including software and hardware. My prior education is in Mechanical Engineering from BUET and I love to work with data-finding trends, analysis and empirical descision makings from data and exploring new things. Mainly work with simulation softwares and use code to scale up processes and getting data driven descisions is my work.

---

###  Core Artifacts
#### [Assisted Neural Network On Input Space Driven Error Manifold Mapping For Better Error Prediction](https://github.com/Aniruddh5502/assisted-nn-error-mapping?tab=readme-ov-file)|*Assisted NN Error Mapping*
This is one of my research works. Basically there are two types of errors/uncertainities in data generated from simulation softwares and then surrogate models trained on them. One there are allhetoric uncertainity and another Epistemic Uncertainity. Now the former is intrinsic to data that was used to train the model. And the latter arrives from the model training processes. Now when the surrogate models are used to predict the outputs in some regression FEA problem, there are several ways in which people can estimate this error, or at least try to predict them using statistics and probability. But that gives a mathamatical probability, which is effective in laws of large numbers, but for a single inference, it becomes hard to predict it accurately or even close enough. Now this new method imbues a incentive to learn the error behaviour of the model. Now this only works if the error changing behaviour of the model is some function of the inputspace. Because that's the only thing we will have at inference time. Now testing this idea gives this result below. We correlate the error quantity predicted by the Error Mapper model and The Absolute error computed form a held out test sets feature and target columns. And we can see a very likely correlation in both Spearman and Pearson correlation. Meaning we we have very high positive Linear and Rank Correlation.

**Performance: Input Driven Error Manifold Mapping and Training**

| Ouput Dimension | Pearson Correlation | Spearman Correlation |
|---|---|---|
| max stress von mises error | 0.89 | 0.88 |
| max deformation error | 0.53 | 0.41 |
| mode 1 frequency error | 0.97 | 0.90 |
| mode 2 frequency error | 0.99 | 0.92 |
| mode 3 frequency error | 0.95 | 0.94 |
| mode 4 frequency error | 0.97 | 0.95 |


#### [Mechanical Design Optimization Framework](https://github.com/Aniruddh5502/mechanical-design-optimization-framework) | *Probabilistic Surrogate Modeling*
This project came out of my University Thesis where I wrote codes for training Surrogate Model on data generated from simulation that was scripted to do parametric sweep over the total design space and generate simulation data. After the training of the Ensemble Neural Network Surrogate model did sensitivity analysis with jacobean, Manifold Extraction of the response surface of the Ensemble Neural Network model to investigate how the manifold looked, but obviously first I had to down project it to 3D to view it. Otherwise there are 6 dimensions in the output of this model which was averaged over the Ensemble members outputs for each dimensions.

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

###  Tech Stack

| Domain | Technologies |
| :--- | :--- |
| **Physical Intelligence** | Surrogate Modeling (ROMs), Probabilistic Optimization, FEA (ANSYS), CFD, SDOF Dynamics |
| **Embedded Systems** | C/C++, ESP32, TMR, OTA Management, RTOS, Hardware Watchdogs, NASA/JPL Safety Standards |
| **AI & Software** | Python, PyTorch, LangGraph, MLP Ensembles, UMAP/PCA, NumPy, Pandas |
| **Tools & Design** | SolidWorks, MATLAB, LaTeX, Blender, Playwright (Automation) |

---

###  Current Trajectory
Working on a research project about **Error Prediction/UQ with assisted neural network for Surrogate models in case of input space/design space dependency of error distribution** for better correlation between absolute error and predicted error/quantized uncertainity.

[Portfolio](https://aniruddh5502.github.io/) | [LinkedIn](https://www.linkedin.com/in/aniruddh2122/)
