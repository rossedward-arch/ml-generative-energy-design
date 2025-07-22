# Portfolio Research extensions 
This document outlines a structured, phase-by-phase journey to build the interdisciplinary knowledge and practical skills required for PhD-level research in **Integrated ML, Generative Design & Energy Simulation for Climate-Adapted Net-Zero Buildings**. Each phase culminates in key deliverables, ensuring a robust foundation for your doctoral studies.

---

## 🧱 Phase 1: Foundations – Python, Data Handling, and Architectural File Parsing
This initial phase focuses on establishing a robust foundation in Python programming, essential data manipulation techniques, and an understanding of common architectural and energy simulation file formats. These core skills are indispensable for effective data preprocessing, interaction with simulation tools, and preparing inputs for machine learning models.

### 🎯 Core Skills & Concepts
* **Python Fundamentals**: Develop strong fluency in core Python syntax, control flow, functions, and file I/O, vital for structuring complex energy analysis scripts.
* **Data Manipulation with Pandas & NumPy**: Master the handling and transformation of tabular data, crucial for processing climate files (EPW, UKCP18) and simulation outputs.
* **Data Visualization**: Utilize Matplotlib and Seaborn to visualize trends in energy data, such as temperature profiles and energy consumption patterns.
* **Energy Modeling Basics & File Formats**: Understand the fundamental concepts of building energy simulation, particularly how data is structured within common formats like EPW, CSV, JSON, and IDF (EnergyPlus).
* **BIM Data Extraction (IFC)**: Explore initial techniques for extracting geometric and non-geometric data from IFC models, a key step for integrating design information.
* **Version Control with Git & GitHub**: Establish a robust workflow for tracking changes, collaborating, and maintaining an organized repository.

### 🧪 Key Mini-Projects & Exercises
* **EPW Weather File Parser & Summary Tool**: Develop a Python script to parse standard EPW weather files, extracting key meteorological data and generating summary statistics.
    * Link to viz_script.py
* **EnergyPlus CSV Output Visualizer**: Create a tool to visualize time-series data from EnergyPlus CSV outputs, such as temperature and humidity, demonstrating data plotting capabilities
    * Link to viz_script.py
* **UKCP18 Climate Scenario Explorer**: Explore and plot local temperature change trends from UKCP18 data, showcasing climate data handling and initial analysis.
    * Link to relevant notebook/script

### 📚 Detailed Learning & Documentation
For a comprehensive breakdown of concepts, code examples, and my daily reflections during this phase, please refer to:
  * [Phase 1 Progress Log](../01_foundation/01_progress_log.md)
  * [Python Notes: Fundamentals](../01_foundation/02_note_python_fundamentals.md)

###  ➡️ Moving Forward
With these foundational skills established, the next phase will delve into Machine Learning for Energy Prediction, building surrogate models to accelerate building performance analysis.

---

## ⚙️ Phase 2: Machine Learning for Energy Prediction
This phase is dedicated to building and applying core machine learning skills, specifically focusing on supervised learning methods, to develop predictive models for building energy performance. These techniques are important for creating efficient surrogate models that can significantly accelerate iterative design and optimization processes.

### 🎯 Core Skills & Concepts
* **Supervised Learning Algorithms**: Gain a solid understanding and practical experience with fundamental regression algorithms (e.g., Linear Regression, Decision Trees, Random Forests) applicable for predicting continuous energy values (e.g., kWh/year, peak loads).
* **Model Evaluation & Tuning**: Develop proficiency in using key metrics (RMSE, R², MAE) for rigorous model assessment and implement techniques like cross-validation and hyperparameter tuning to ensure reliability and prevent overfitting.
* **Feature Engineering & Selection**: Explore methods for transforming raw simulation and climate datasets into effective features for ML models, including data cleaning, handling missing values, and selecting impactful variables.
* **Data Pipelines & Preprocessing**: Establish foundational data processing pipelines to efficiently prepare real-world simulation and climate datasets for machine learning training, ensuring quality and consistency.
* **Tools**: Gain hands-on proficiency with scikit-learn for supervised learning and Jupyter notebooks for interactive development. Begin exploring PyTorch for basic neural network concepts.

### 🧪 Key Mini-Projects & Exercises
* **Annual Heating Load Predictor**: Develop and train ML models to predict annual heating loads using building parameters and climate data, demonstrating energy-specific predictive modeling.
    * Link to train_model.py
* **ML Model Comparison for Energy Use**: Implement and systematically compare different supervised ML models for predicting building energy use, analyzing their strengths and weaknesses.
    *Link to notebooks/01_ml_model_comparison.ipynb
* **Cross-Validation and Hyperparameter Tuning Experiment**: Apply robust validation techniques and perform initial hyperparameter tuning to optimize predictive accuracy for energy consumption.
    * Link to notebooks/02_model_tuning_validation.ipynb
* **Simple Neural Network in PyTorch**: Implement a basic feedforward neural network in PyTorch for a regression task (e.g., simplified energy prediction), gaining foundational experience with deep learning frameworks.
    * Link to notebooks/03_pytorch_intro_nn.ipynb

### 📚 Detailed Learning & Documentatio
For a comprehensive breakdown of concepts, code examples, and my daily reflections during this phase, please refer to:
* [Phase 2 Progress Log](../02_ml_predictions/01_progress_log.mdd)
* [Notes on Scikit-learn Basics](../02_ml_predictions/02_notes_sklearn_basics.md)
* [Notes on PyTorch Introduction](../02_ml_predictions/03_notes_pytorch_intro.md)
* [Notes on Dataset Preparation for ML](../02_ml_predictions/04_dataset__preperation.md)

### ➡️ Moving Forward
Building upon these predictive capabilities and model evaluation skills, the next phase will integrate these ML models directly into Generative Design workflows.

---

## 🕹️ Phase 3: ML-Integrated Generative Design
This phase integrates the machine learning models developed in Phase 2 with parametric and generative design workflows. The goal is to leverage ML surrogates to efficiently explore vast architectural design spaces, optimizing for energy performance and other critical building metrics. This integration is a cornerstone for creating intelligent design tools capable of rapid iteration and performance-driven decision-making.

### 🎯 Core Skills & Concepts
* **Parametric Modeling with Grasshopper & Rhino**: Gain proficiency in creating flexible, rule-based geometric models in Grasshopper, essential for defining design variables and generating numerous design alternatives.
* **Surrogate Modeling & ML Model Deployment**: Learn to effectively deploy pre-trained ML models as fast-running "surrogates" within design optimization loops, significantly reducing the computational cost of high-fidelity simulations.
* **Optimization Techniques**: Explore and apply various optimization algorithms, including Genetic Algorithms (GAs) for exploring design permutations and Bayesian Optimization for more sample-efficient search.
* **Visualization of Design Iterations & Results**: Develop methods to visually represent the design space, optimization progression, and trade-offs between multiple performance objectives (e.g., energy use vs. daylighting).
* **Integration of ML Feedback**: Understand how to programmatically connect ML model outputs (predictions) back into the parametric design environment, allowing the generative process to be directly informed by performance insights.

### 🧪 Key Mini-Projects & Exercises
This phase embodies the core of your PhD research—linking generative design with ML-driven energy performance prediction, enabling rapid, informed architectural design iterations.
* **Parametric Model with ML Surrogate Fitness Function**: Create a foundational parametric building model in Grasshopper. Integrate a trained ML surrogate to serve as the fitness function for optimization, linking design parameters directly to predicted energy performance.
    * Link to relevant Grasshopper file and Python script
* Building Orientation or Window Size Optimization: Implement a generative design workflow to optimize specific building parameters using the ML surrogate for rapid energy performance evaluation.
    * Link to relevant notebook/script
* **Simple Generative Design Workflow with ML Integration**: Develop an end-to-end workflow demonstrating how generative algorithms can propose designs, feed parameters to an ML surrogate, and use predictions to refine subsequent generations.
    * Link to relevant notebook/script
* **Pareto Front Visualization for Multi-Objective Optimization**: Visualize the Pareto front for design alternatives, demonstrating trade-offs between conflicting objectives (e.g., minimizing energy use while maximizing daylighting).
    * Link to relevant visualization script or notebook

### 📚 Detailed Learning & Documentation
For a comprehensive breakdown of concepts, code examples, and my daily reflections during this phase, please refer to:
* [Phase 3 Progress Log](../03_generative_design/01_progress_log.md)
* [Notes on Parametric Design](../03_generative_design/02_notes_parametric_design.md)
* [Notes on Generative Algorithms](../03_generative_design/03_notes_generative_algorithms.md)
  
### ➡️ Moving Forward
With the ability to integrate ML models into generative design workflows, the next critical step (Phase 4) will focus on establishing **Simulation-ML Feedback Loops**.

---

## 🔄 Phase 4: Simulation-ML Feedback Loops and Automation
This important phase focuses on establishing robust, iterative feedback loops between high-fidelity building energy simulations and machine learning models. The primary goal is to develop workflows where simulation results continuously train and refine ML surrogates, enabling more accurate and adaptive design optimization. This phase also introduces the foundational concepts of Reinforcement Learning (RL) as a powerful paradigm for guiding complex, sequential design decisions.

### 🎯 Core Skills & Concepts
* **Building Energy Simulation Tools Proficiency**: Gain advanced hands-on experience with industry-standard tools like EnergyPlus and OpenStudio, understanding their capabilities for detailed performance analysis.
* **Automating Simulations & Output Collection**: Develop robust Python scripts (using libraries like Eppy or OpenStudio SDK bindings) to programmatically run batch simulations and efficiently parse/collect large volumes of output data.
* **Iterative ML Model Training & Refinement**: Master techniques for training and retraining ML surrogate models using newly generated simulation data, including strategies for data cleaning, feature engineering, and model validation.
* **Reinforcement Learning (RL) Fundamentals**: Acquire a foundational understanding of RL principles, including agents, environments, states, actions, rewards, and policies, exploring how design optimization can be framed as a sequential decision-making problem.
* **Adaptive Optimization Methods**: Begin to explore how RL and other adaptive optimization techniques can dynamically guide the design search process, learning from simulation feedback to converge on optimal solutions more efficiently.
* **Multi-Objective Optimization Concepts**: Reinforce understanding of multi-objective optimization, recognizing the need to balance conflicting design goals (e.g., minimizing energy use while maximizing thermal comfort or minimizing cost).

### 🧪 Key Mini-Projects & Exercises
* **Automated EnergyPlus Parametric Simulations**: Develop a Python script to programmatically generate multiple EnergyPlus input files, run simulations for each, and extract key performance indicators (KPIs) into a structured dataset.
    * Link to relevant script
* **Surrogate Model Training and Error Analysis**: Train a new ML surrogate model using automated simulation data. Critically analyze its approximation error against high-fidelity results.
    * Link to relevant notebook/script
* **Iterative Simulation–ML Feedback Loop Implementation**: Develop a proof-of-concept workflow where generative design proposes designs, an ML surrogate provides estimates, and promising designs feed back to high-fidelity simulation for retraining.
    * Link to relevant notebook/script
* **Basic Reinforcement Learning Agent for Design Task**: Implement a simple RL agent in a simplified environment (e.g., using OpenAI Gym concepts) to solve a basic architectural optimization problem (e.g., finding optimal window shading angles).
    * Link to relevant notebook/script
* **Multi-Objective Design Exploration**: Explore methods for visualizing and analyzing multi-objective optimization results (e.g., Pareto fronts) from simulation-ML feedback loops.
    * Link to relevant visualization script or notebook

### 📚 Detailed Learning & Documentation
For a comprehensive breakdown of concepts, code examples, and my daily reflections during this phase, please refer to:
* [Phase 4 Progress Log](../04_feedback_optimisation/01_progress_log.md)
* [Notes on Simulation-ML Loops](../04_feedback_optimisation/02_notes_simulation_ml_loops.md)
* [Notes on Multi-Objective Optimization](../04_feedback_optimisation/03_notes_multi_objective_optimisation.md)
* [Notes on Reinforcement Learning Fundamentals](../04_feedback_optimisation/04_notes_reinforcement_learning_fundamentals.md)

### ➡️ Moving Forward
With a solid understanding of simulation-ML feedback loops and the foundations of Reinforcement Learning, the final phase (Phase 5) will delve into Portfolio & Research Extensions.

---

## 🔬 Phase 5: Portfolio & Research Extensions (18–24 months)
This culminating phase consolidates all learned skills and developed projects into a professional portfolio, while also exploring advanced research topics that align with climate-adapted net-zero building design. The goal is to prepare for PhD proposal defenses, academic publication, and to define the specific research trajectory for my doctoral work.

### 🎯 Core Skills & Concepts
* **Research Communication & Portfolio Development**: Consolidate all project outputs into a professional online portfolio, clearly presenting research contributions and findings.
* **Advanced Reinforcement Learning (Optional Deep Dive)**: Further explore advanced RL algorithms (e.g., Actor-Critic methods, DRL for complex control) if directly applicable to dynamic building operation or complex sequential design problems.
* **Explainable AI (XAI) in AEC/Building Science**: Investigate methods to interpret and explain the predictions of ML models used in building design and energy analysis, crucial for building trust and enabling human-AI collaboration.
* **Climate Adaptation Strategies Integration**: Deepen understanding and implement methodologies for integrating climate change adaptation strategies (e.g., future weather files, passive resilience) into generative design and simulation workflows.
* **Whole-Life Carbon (WLC) Modeling**: Explore concepts and tools for assessing embodied and operational carbon across the building lifecycle, extending optimization objectives beyond operational energy.
* **Academic Writing & Presentation**: Refine skills in academic writing, research proposal development, and effective presentation for conferences and publications.

### 🧪 Key Mini-Projects & Exercises
* **Professional Online Portfolio**: Develop and launch a polished online portfolio showcasing your Python projects, ML models, generative design workflows, and simulation automation scripts.
    * Link to your portfolio website
* **Case Studies on Climate-Adaptive Generative Design**: Document one or more detailed case studies demonstrating how your integrated approach leads to climate-resilient and energy-efficient building designs.
    * Link to case study report/notebook
* **Explainable AI for Energy Prediction Models**: Apply XAI techniques (e.g., SHAP, LIME) to your trained ML energy prediction models to interpret feature importance and model decision-making processes.
    * Link to XAI notebook/script
* **Simple Whole-Life Carbon Assessment Integration**: Develop a conceptual framework or a basic script that integrates a simplified whole-life carbon assessment into your design evaluation loop.
    * Link to relevant notebook/script
* **Research Proposal Draft**: Prepare a preliminary PhD research proposal outlining your specific research questions, methodology, and anticipated contributions.
    * Link to proposal draft

### 📚 Detailed Learning & Documentation
For a comprehensive breakdown of concepts, code examples, and my daily reflections during this phase, please refer to:
* [Phase 5 Progress Log](../05_portfolio_research_extensions/01_progress_log.md)
* [Notes on Advanced RL & XAI](../05_portfolio_research_extensions/02_notes_advanced_rl_xai.md)
* [Notes on Climate Adaptation](../05_portfolio_research_extensions/03_notes_climate_adaptation.md) & [WLC](../05_portfolio_research_extensions/04_notes_whole_life_carbon.md)
* [Notes on Academic Writing & Publishing](../05_portfolio_research_extensions/05_notes_academic_writing_publishing)

### ➡️ Moving Forward
This phase culminates in a portfolio and a well-defined research direction, signifying readiness for a successful PhD journey focused on Integrated ML, Generative Design & Energy Simulation for Climate-Adapted Net-Zero Buildings.

---

### 📈 General Recommendations for Success
* **Regular Checkpoints**: Schedule bi-weekly or monthly reviews to assess progress, adjust goals, and incorporate feedback from mentors or peers.
* **Comprehensive Documentation**: Maintain clear, detailed notes and comments for all code, experiments, and learnings to facilitate knowledge transfer and future publication.
* **Effective Version Control**: Utilize GitHub repositories with clear commit messages, branching strategies, and issue tracking for robust project management and collaboration.
* **Community Engagement**: Actively participate in relevant online forums, academic communities, or open-source projects to gain insights, seek help, and explore collaboration opportunities.
* **Robust Data Management**: Implement regular backup strategies for datasets, models, and scripts to prevent data loss and ensure research reproducibility.

---

# General Recommendations

* **Regular Checkpoints:** Schedule biweekly or monthly reviews to assess progress, adjust goals, and incorporate feedback.
* **Documentation:** Keep clear, detailed notes and comments to facilitate knowledge transfer and future publication.
* **Version Control:** Use GitHub repositories with clear commit messages and issue tracking.
* **Community Engagement:** Share progress in relevant online forums or with academic peers to gain insights and collaboration opportunities.
* **Backup & Data Management:** Regularly back up datasets, models, and scripts to avoid data loss.

---

