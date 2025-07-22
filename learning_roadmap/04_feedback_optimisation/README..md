# 🔄 Phase 4: Simulation-ML Feedback Loops (12–18 months)

This pivotal phase focuses on establishing robust, iterative feedback loops between high-fidelity building energy simulations and machine learning models. The primary goal is to develop workflows where simulation results are used to continuously train and refine ML surrogates, enabling more accurate and adaptive design optimization. This phase also introduces the foundational concepts of Reinforcement Learning (RL) as a powerful paradigm for guiding complex, sequential design decisions in the pursuit of climate-adapted, net-zero buildings.

## 🎯 Core Skills & Concepts 

* **Building Energy Simulation Tools Proficiency:** Gained advanced hands-on experience with industry-standard building energy simulation tools like EnergyPlus and OpenStudio, understanding their capabilities for detailed performance analysis.
* **Automating Simulations & Output Collection:** Developed robust Python scripts (e.g., using libraries like Eppy or OpenStudio SDK bindings) to programmatically modify simulation inputs, run batch simulations across parametric variations or climate scenarios, and efficiently parse/collect large volumes of output data.
* **Iterative ML Model Training & Refinement:** Mastered techniques for training and, crucially, *retraining* ML surrogate models using newly generated simulation data. This includes strategies for data cleaning, feature engineering, and model validation to ensure the surrogates remain accurate and generalizable.
* **Reinforcement Learning (RL) Fundamentals:** Acquired a foundational understanding of Reinforcement Learning principles, including concepts such as agents, environments, states, actions, rewards, and policies. Explored how design optimization can be framed as a sequential decision-making problem for an RL agent.
* **Adaptive Optimization Methods:** Began to explore how RL and other adaptive optimization techniques can dynamically guide the design search process, learning from simulation feedback to converge on optimal or near-optimal solutions more efficiently.
* **Multi-objective Optimization Concepts:** Reinforced understanding of multi-objective optimization, recognizing the need to balance conflicting design goals (e.g., minimizing energy use while maximizing thermal comfort or minimizing cost).

## 🧪 Key Mini-Projects & Exercises 

* **Automated EnergyPlus Parametric Simulations:** Developed a Python script to programmatically generate multiple EnergyPlus input files (`.idf`), run simulations for each, and extract key performance indicators (KPIs) like EUI, peak loads, and discomfort hours into a structured dataset.
    * [Link to relevant script, e.g., `src/simulation_automation/run_parametric_sims.py`](your_github_link_to_file)*(link when build)*
* **Surrogate Model Training and Error Analysis:** Trained a new ML surrogate model using a dataset generated from automated simulations. Critically analyzed the surrogate's approximation error against high-fidelity simulation results, identifying areas for improvement.
    * [Link to relevant notebook/script, e.g., `notebooks/01_surrogate_retraining_analysis.ipynb`](your_github_link_to_file)*(link when build)*
* **Iterative Simulation–ML Feedback Loop Implementation:** Developed a proof-of-concept workflow where a generative design algorithm proposes designs, an ML surrogate provides quick performance estimates, and a subset of promising designs are sent to high-fidelity simulation, with results feeding back to retrain the surrogate.
    * [Link to relevant notebook/script, e.g., `notebooks/02_iterative_feedback_loop.ipynb`](your_github_link_to_file)*(link when build)*
* **Basic Reinforcement Learning Agent for Design Task:** Implemented a simple RL agent in a simplified, custom environment (e.g., using OpenAI Gym concepts) to solve a basic architectural optimization problem (e.g., finding optimal window shading angles for a fixed period). This demonstrated the core RL loop.
    * [Link to relevant notebook/script, e.g., `mini_projects/04_rl_basics/simple_shading_agent.py`](your_github_link_to_file) *(link when build)*
* **Multi-Objective Design Exploration:** Explored methods for visualizing and analyzing multi-objective optimization results (e.g., Pareto fronts) from simulation-ML feedback loops, demonstrating the ability to identify optimal trade-off solutions for designers.
    * [Link to relevant visualization script or notebook, e.g., `notebooks/03_multi_objective_viz.ipynb`](your_github_link_to_file) *(link when build)*

## 📚 Key Readings & Resources

* *Energy Simulation in Building Design* (Joseph Clarke) – Advanced chapters on automation, calibration, and model-based design.
* *Reinforcement Learning: An Introduction* (Sutton & Barto) – Selected introductory chapters (e.g., on MDPs, value functions, policy iteration) for a theoretical foundation in RL.
* Stable Baselines3 documentation and tutorials ([stable-baselines3.readthedocs.io](https://stable-baselines3.readthedocs.io/en/master/)) – Practical guide for implementing modern RL algorithms in Python.
* Research articles on simulation-ML integration, reinforcement learning in building design, and adaptive optimization.
* *Net Zero Energy Buildings* (Linda Reeder) - Good intro to high-performance building design, providing context for optimization targets.

## 📚 Detailed Learning & Documentation

For a comprehensive breakdown of concepts, code examples, and my daily reflections during this phase, please refer to:

* [**Phase 4 Progress Log**](01_progress_log.md) 
* [**Notes on Simulation-ML Loops**](02_notes_simulation_ml_loops.md)
* [**Notes on Multi-Objective Optimization**](03_notes_multi_objective_optimization.md)
* [**Notes on Reinforcement Learning Fundamentals**](04_notes_reinforcement_learning_fundamentals.md) 

## ➡️ Moving Forward

With a solid understanding of simulation-ML feedback loops and the foundations of Reinforcement Learning, the final phase (Phase 5) will delve into **Portfolio & Research Extensions**. This will involve deepening expertise in advanced RL and Explainable AI, integrating climate adaptation strategies, and exploring whole-life carbon modeling to create a comprehensive, PhD-ready research portfolio.