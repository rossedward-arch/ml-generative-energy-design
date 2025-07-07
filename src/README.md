📂 Source Code

This folder contains the core Python modules and scripts that implement the fundamental logic and components of the ML-Driven Generative Design for Energy-Efficient Buildings project. This is where reusable, structured, and production-oriented code resides, moving beyond the exploratory phase of Jupyter notebooks.

---

### 🗂️ Folder Structure & Modules Overview

This directory is organized into thematic sub-folders to ensure modularity, scalability, and ease of navigation:

* **`data_processing/`**
    * **Purpose:** Contains scripts and functions for cleaning, transforming, and preparing raw datasets into model-ready formats. This includes handling EPW data, processing geometry features, and aligning simulation outputs.
    * **Example Files:** `preprocessing.py`, `feature_engineering.py`, `data_loaders.py`

* **`models/`**
    * **Purpose:** Houses the definitions and training logic for various machine learning models.
    * **Contents:**
        * `energy_predictor.py`: Classes and functions for your energy prediction surrogate models (e.g., neural networks, tree-based models).
        * `model_training.py`: Scripts to manage the training, validation, and saving of these models.
        * `model_evaluation.py`: Functions for calculating performance metrics and generating evaluation plots.

* **`generative_design/`**
    * **Purpose:** Implements the core algorithms and logic for generating and evolving architectural designs.
    * **Contents:**
        * `algorithms.py`: Implementations of generative algorithms (e.g., genetic algorithms, rule-based generators).
        * `design_representation.py`: Defines classes and methods for representing architectural designs in a machine-readable format.
        * `constraints.py`: Logic for applying and validating architectural constraints.

* **`simulation_interface/`**
    * **Purpose:** Provides an interface to interact with external building performance simulation tools.
    * **Contents:**
        * `energyplus_api.py`: Scripts for generating EnergyPlus input files (IDF), running simulations, and parsing output files (e.g., `eplusout.sql`, `html`).
        * `ladybug_openstudio_integration.py`: Functions for programmatically interacting with Ladybug Tools and OpenStudio SDK.

* **`rl_agents/`**
    * **Purpose:** Contains the implementation of Reinforcement Learning agents and their environments for design optimization.
    * **Contents:**
        * `rl_environment.py`: Defines the custom OpenAI Gym-like environment for architectural design.
        * `agent_definitions.py`: Classes for specific RL agents (e.g., DQN, PPO, SAC).
        * `training_loops.py`: Scripts for training and evaluating RL agents.

* **`xai_modules/`**
    * **Purpose:** Houses code for implementing and applying Explainable AI techniques to your ML models.
    * **Contents:**
        * `shap_explainers.py`: Custom wrappers or utilities for SHAP library integration.
        * `lime_explainers.py`: Custom wrappers or utilities for LIME library integration.
        * `interpretation_visuals.py`: Functions for generating interpretable visualizations.

* **`utils/`**
    * **Purpose:** General utility functions that are used across different modules but don't belong to a specific functional area.
    * **Contents:** `plot_helpers.py`, `config_loader.py`, `common_calculations.py`, etc.

---

### 📝 Usage Notes

* These structured modules are designed to be **imported and utilized** by Jupyter notebooks for experimentation and from higher-level pipeline scripts (e.g., in `app/` or dedicated research pipelines) for batch runs and system integration.
* The code prioritizes **readability, modularity, and reusability**, enabling easy extension and integration as the project evolves.
* Ongoing development includes **refactoring** to improve performance, maintainability, and adherence to best practices.

---

### 🚀 Next Steps for Source Code Development

* Implement **automated testing** (e.g., using `pytest`) for core modules to ensure robustness and prevent regressions.
* Integrate **type hinting** and **docstrings** comprehensively throughout the codebase for improved clarity and maintainability.
* Expand API coverage for more energy simulation engines and direct integration with BIM software.
* Optimize generative algorithm parameters and core ML models for improved performance and efficiency.
* Explore advanced **parallelization strategies** for simulation runs and model training where applicable.
