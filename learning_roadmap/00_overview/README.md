# 🚀 PhD Readiness Project Guide: Overview

This repository documents a structured self-learning roadmap designed to build comprehensive expertise in Machine Learning (ML), Generative Design, and Building Energy Simulation for the development of Climate-Adapted, Net-Zero Buildings. This initiative serves as a foundational "PhD Readiness Project" to prepare for advanced research in this interdisciplinary field.

---

## 🎯 Project Vision & Goals

My goal is to integrate computational methods into architectural design, specifically focusing on:
* **Accelerating Performance Simulation**: Using ML (e.g., surrogate models) to provide rapid feedback on energy performance.
* **Exploring Design Space**: Leveraging generative design and optimization techniques to discover novel, high-performing architectural solutions.
* **Climate Adaptation**: Integrating climate data and future scenarios to create resilient and adaptable buildings.
* **Net-Zero Focus**: Targeting strategies for drastically reducing operational and embodied carbon.

This roadmap outlines a progressive journey, from foundational programming skills to advanced research concepts, with tangible mini-projects and detailed documentation at each step.

---

## 🗺️ Roadmap Phases

The entire readiness project is structured into five distinct phases, each building upon the last, culminating in a robust set of skills and a research-ready portfolio.

### 🧱 Phase 1: Foundations – Python, Data Handling, and Architectural File Parsing
  * **Duration**: 0–3 months
  * **Focus**: Core Python, data manipulation (Pandas, NumPy), data visualization, understanding energy/BIM file formats (EPW, CSV, IFC), and Git/GitHub fundamentals.
  * **Go to Detailed Phase 1 README**: [README.md](../01_foundation/README.md)

### ⚙️ Phase 2: Machine Learning for Energy Prediction
  * **Duration**: 3–6 months
  * **Focus**: Supervised learning algorithms (Linear Regression, Decision Trees, Random Forests), model evaluation (MAE, RMSE, R²), cross-validation, hyperparameter tuning, feature engineering, scikit-learn, Jupyter notebooks, basic PyTorch.
  * **Go to Detailed Phase 2 README**: [README.md](../02_ml_predictions/README.md)

### 🕹️ Phase 3: ML-Integrated Generative Design
  * **Duration**: 6–12 months
  * **Focus**: Parametric modeling (Grasshopper, Rhino), deploying ML surrogates as fitness functions, optimization techniques (Genetic Algorithms, Bayesian Optimization), and visualizing design space exploration.
  * **Go to Detailed Phase 3 README**: [README.md](../03_generative_design/README.md)

### 🔄 Phase 4: Simulation-ML Feedback Loops and Automation
  * **Duration**: 12–18 months
  * **Focus**: Advanced building energy simulation tools (EnergyPlus, OpenStudio), automating simulation runs, iterative ML model retraining, foundational Reinforcement Learning (RL), and adaptive optimization.
  * **Go to Detailed Phase 4 README**: [README.md](../04_feedback_optimisation/README.md)

### 🔬 Phase 5: Portfolio & Research Extensions
  * **Duration**: 18+ months & Ongoing
  * **Focus**: Consolidating project outputs into a professional portfolio, advanced RL, Explainable AI (XAI), climate adaptation strategies, Whole-Life Carbon (WLC) modeling, and preparing for PhD proposal defense/publication.
  * **Go to Detailed Phase 5 README**: [README.md](../05_portfolio_research_extensions/README.md)

## 📂 Repository Structure

The repository is organized to reflect the phased learning roadmap and store all associated code, notes, and resources:
```text
learning_roadmap/ # Main directory containing the entire PhD readiness learning roadmap.
                  # This structure guides a systematic progression through key skills.
├── 00_overview/  # Contains high-level documents providing an overview of the entire roadmap,
                  # general resources, and administrative items.
│   ├── 01_checklist.md          # A checklist for tracking overall progress or specific tasks.
│   ├── 02_reference.md          # General reference notes or summaries applicable across phases.
│   ├── 03_tutorials_links.md    # A curated list of external tutorials and useful links.
│   └── README.md                # The primary entry point for the entire learning_roadmap,
│                                # summarizing the vision, phases, and how to navigate the repo.
│
├── 01_foundation/               # Phase 1: Focuses on core Python programming, data handling,
│                                # and fundamental energy/architectural data formats.
│   ├── 01_progress_log.md       # Detailed daily/weekly log of learning activities and progress for Phase 1.
│   ├── 02_note_python_fundamentals.md # Notes on core Python concepts (syntax, data structures, functions, etc.).
│   ├── 03_notes_energyplus.md   # Notes related to EnergyPlus simulation basics and concepts.
│   ├── 04_notes_energy_file_formats.md # Documentation on EPW, IDF, CSV, JSON, etc. file formats.
│   ├── 05_notes_numpy_for_data.md # Notes on NumPy library for numerical operations.
│   ├── 06_notes_pandas_data_manipulation.md # Notes on Pandas for data structuring and manipulation.
│   ├── 07_notes_data_visualization.md # Notes on Matplotlib/Seaborn for data plotting.
│   └── README.md                # Detailed overview, skills, mini-projects, and links for Phase 1.
│
├── 02_ml_predictions/           # Phase 2: Dedicated to Machine Learning for building energy prediction,
│                                # focusing on supervised learning.
│   ├── 01_progress_logs.md      # Progress log for Phase 2.
│   ├── 02_notes_sklearn_basics.md # Notes on Scikit-learn for ML algorithm implementation.
│   ├── 03_notes_pytorch_intro.md # Introduction to PyTorch for deep learning fundamentals.
│   ├── 04_dataset_preparation.md # Notes on preparing and cleaning datasets for ML models.
│   └── README.md                # Detailed overview, skills and links for Phase 2.
│
├── 03_generative_design/        # Phase 3: Integration of ML models with parametric and generative
│                                # design workflows.
│   ├── 01_progress_log.md       # Progress log for Phase 3.
│   ├── 02_notes_parametric_design.md # Notes on parametric modeling concepts (e.g., Grasshopper, Rhino).
│   ├── 03_notes_generative_algorithms.md # Notes on algorithms like Genetic Algorithms, Bayesian Optimization.
│   └── README.md                # Detailed overview, skills and links for Phase 3.
│
├── 04_feedback_optimisation/    # Phase 4: Focuses on establishing iterative feedback loops between
│                                # high-fidelity simulations and ML models, and introducing RL.
│   ├── 01_progress_log.md       # Progress log for Phase 4.
│   ├── 02_notes_simulation_ml_loops.md # Notes on automating simulations and integrating with ML retraining.
│   ├── 03_notes_multi_objective_optimisation.md # Notes on balancing conflicting design objectives.
│   ├── 04_notes_reinforcement_learning_fundamentals.md # Foundational concepts of Reinforcement Learning.
│   └── README.md                # Detailed overview, skills, mini-projects, and links for Phase 4.
│
├── 05_portfolio_research_extensions/ # Phase 5: Culminating phase for portfolio development,
│                                     # advanced research topics, and PhD readiness.
│   ├── 01_progress_log.md            # Progress log for Phase 5.
│   ├── 02_notes_advanced_rl_xai.md   # Notes on advanced RL techniques and Explainable AI (XAI).
│   ├── 03_notes_climate_adaptation.md # Notes on strategies for climate-resilient building design.
│   ├── 04_notes_whole_life_carbon.md # Notes on assessing embodied and operational carbon over a building's lifecycle.
│   ├── 05_notes_academic_writing_publishing.md # Notes on structuring research, proposals, and publications.
│   └── README.md                     # Detailed overview, skills, mini-projects, and links for Phase 5.
│
├── mini_projects/ # A dedicated directory for standalone, practical coding exercises and
│                  # small applications demonstrating learned skills from various phases.
│   ├── 01_parse_epw_weather_files/      # Project: Script to parse and extract data from EPW weather files.
│   ├── 02_visualize_energyplus_csv_outputs/ # Project: Tool to visualize time-series data from EnergyPlus CSVs.
│   └── 03_train_ml_models_energy_performance/ # Project: Code for training ML models for energy prediction.
│
└── 06_archive/  # Contains outdated, deprecated, or less relevant content that is kept for record,
                 # but is not actively part of the core roadmap.
    └── README.md # Explanation of content within the archive.
```

## 📈 General Recommendations for Success
This roadmap adheres to best practices for self-directed learning and project management:
* **Regular Checkpoints**: Scheduled reviews to assess progress, adjust goals, and incorporate feedback.
* **Comprehensive Documentation**: Clear, detailed notes and comments for all code, experiments, and learnings.
* **Effective Version Control**: Consistent use of Git and GitHub for tracking changes and managing the repository.
* **Community Engagement**: Active participation in relevant online forums or with academic peers.
* **Robust Data Management**: Regular backup strategies for datasets, models, and scripts.

