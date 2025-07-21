# PhD Readiness Learning Roadmap Checklist

*Integrating ML, Generative Design & Energy Simulation for Architecture*

---

## ✅ Phase 1: Foundations (0–3 months)

### 🎯 Core Skills & Concepts
- [ ] Learn Python syntax: variables, loops, functions, file I/O
- [ ] Explore Python data science libs: `pandas`, `numpy`, `matplotlib`, `seaborn`
- [ ] Understand architectural file formats: CSV, JSON, EPW (weather), IDF (EnergyPlus), IFC, gbXML
- [ ] Review Passivhaus & Net Zero architecture concepts
- [ ] Understand basics of EnergyPlus and OpenStudio energy simulation tools
- [ ] Learn IFC extraction techniques (Revit/Dynamo)
- [ ] Learn Version control basics: Git and GitHub

### 📘 Key Readings & Resources
- [ ] *Python for Data Analysis*, Wes McKinney – Ch. 1, 3, 5
- [ ] *Energy Simulation in Building Design*, Joseph Clarke – Ch. 2, 4
- [ ] Python Official Tutorial ([docs.python.org](https://docs.python.org/3/tutorial/))
- [ ] EnergyPlus Documentation ([energyplus.net](https://energyplus.net/documentation))
- [ ] Ladybug Tools Tutorials ([ladybug.tools/tutorials.html](https://www.ladybug.tools/tutorials.html))
- [ ] IFC Format Overview ([buildingsmart.org](https://technical.buildingsmart.org/standards/ifc/))
- [ ] Dynamo BIM Tutorials ([dynamobim.org/learn](https://dynamobim.org/learn/))

### 🧪 Mini-Projects & Exercises
- [ ] Create a Python parser for EPW weather files
- [ ] Build CSV data visualizer (e.g., temperature vs time)
- [ ] Practice reading/writing JSON, CSV, IDF files using Python
- [ ] Write Python functions practicing loops, conditionals, and file I/O

---

## ✅ Phase 2: Machine Learning for Energy Prediction (3–6 months)

### 🎯 Core Skills & Concepts
- [ ] Learn supervised learning basics: regression, classification
- [ ] Understand train-test splits, cross-validation
- [ ] Explore scikit-learn ML models: Linear Regression, Decision Trees, Random Forest, SVM
- [ ] Learn feature engineering and data preprocessing
- [ ] Understand error metrics: RMSE, MAE, R²
- [ ] Get started with PyTorch for basic Neural Networks

### 📘 Key Readings & Resources
- [ ] *Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow*, Aurélien Géron – Ch. 1, 2, 4
- [ ] Scikit-learn User Guide ([scikit-learn.org](https://scikit-learn.org/stable/user_guide.html))
- [ ] PyTorch official tutorials ([pytorch.org/tutorials](https://pytorch.org/tutorials))
- [ ] Relevant academic papers on ML for building energy prediction

### 🧪 Mini-Projects & Exercises
- [ ] Build an ML model to predict building energy consumption from weather and design data
- [ ] Experiment with feature selection and hyperparameter tuning
- [ ] Evaluate models using RMSE, MAE, and R²
- [ ] Visualize ML model results and error distributions
- [ ] Implement a simple feedforward neural network in PyTorch for a regression task

---

## ✅ Phase 3: ML-Integrated Generative Design (6–12 months)

### 🎯 Core Skills & Concepts
- [ ] Learn parametric design using Grasshopper & Ladybug Tools
- [ ] Understand generative design principles and evolutionary algorithms (e.g., Genetic Algorithms, Particle Swarm Optimization)
- [ ] Integrate ML model predictions (surrogates) into generative design workflows as fitness functions
- [ ] Study designer-in-the-loop feedback methods and visualization of design iterations

### 📘 Key Readings & Resources
- [ ] *Generative Design: Visualize, Program, and Create with JavaScript in p5.js*, Hartmut Bohnacker et al. (select relevant chapters on principles)
- [ ] Ladybug Tools advanced tutorials
- [ ] Academic papers on surrogate-assisted optimization in architecture
- [ ] Resources on Python libraries for optimization (e.g., DEAP, PySwarms)

### 🧪 Mini-Projects & Exercises
- [ ] Create a parametric model of a building facade or room layout in Grasshopper
- [ ] Integrate ML surrogate model for energy prediction into a generative design loop
- [ ] Implement feedback from simulation results to refine design parameters
- [ ] Test generative algorithms for optimizing energy efficiency based on ML predictions
- [ ] Visualize the design iteration process and convergence

---

## ✅ Phase 4: Simulation-ML Feedback Loops (12–18 months)

### 🎯 Core Skills & Concepts
- [ ] Learn to automate EnergyPlus/OpenStudio runs with Python scripts (e.g., using Eppy)
- [ ] Understand model retraining using simulation outputs for surrogate model refinement
- [ ] Study **Reinforcement Learning (RL) fundamentals and adaptive optimization methods**
- [ ] Learn to define and set up RL environments for design exploration tasks (e.g., using OpenAI Gym concepts)
- [ ] Explore multi-objective optimization techniques (concepts and basic implementations)

### 📘 Key Readings & Resources
- [ ] EnergyPlus Advanced Topics Documentation on automation and scripting
- [ ] Papers on ML retraining & feedback in simulation-based design
- [ ] *Reinforcement Learning: An Introduction* (Sutton & Barto) - selected introductory chapters
- [ ] Stable Baselines3 documentation and tutorials ([stable-baselines3.readthedocs.io](https://stable-baselines3.readthedocs.io/en/master/))
- [ ] Academic articles on simulation-ML integration and reinforcement learning in building design

### 🧪 Mini-Projects & Exercises
- [ ] Automate EnergyPlus simulations with parametric inputs and extract key outputs for ML training
- [ ] Build a simple retraining pipeline: simulation data generation → data smoothing → ML model update
- [ ] Implement a basic RL agent for a design optimization task in a controlled, simplified environment
- [ ] Develop an iterative feedback loop combining building energy simulation and ML model predictions
- [ ] Prototype multi-objective optimization considering energy and other performance metrics

---

## ✅ Phase 5: Portfolio & Research Extensions (18+ months & Ongoing)

### 🎯 Core Skills & Concepts
- [ ] Structure code projects professionally for GitHub, including advanced Git branching and pull requests
- [ ] Learn cloud computing basics for scalable simulations and ML model deployment (e.g., AWS, GCP fundamentals)
- [ ] Explore **Explainable AI (XAI)** techniques (e.g., SHAP, LIME, Feature Importance) for model interpretability
- [ ] Investigate **Reinforcement Learning (RL)** advanced topics and specific algorithms (e.g., PPO, SAC)
- [ ] Study **Climate Adaptation** strategies and resilience modeling in architectural design
- [ ] Understand **Whole-Life Carbon (WLC)** assessment principles and explore its integration into design optimization
- [ ] Develop advanced visualization and dashboarding techniques (Plotly, Dash, Streamlit)
- [ ] Learn about co-simulation methods and user-in-the-loop design principles for complex systems
- [ ] Review advanced data cleaning, feature engineering, and dimensionality reduction techniques
- [ ] Understand concepts of post-occupancy calibration and model updating with real-world data

### 📘 Key Readings & Resources
- [ ] GitHub Guides ([guides.github.com](https://guides.github.com/)) on advanced Git
- [ ] Cloud computing tutorials (AWS/GCP basics for compute instances, storage)
- [ ] Papers/tutorials on Explainable AI (XAI) in building simulation and architecture (e.g., SHAP documentation, LIME papers)
- [ ] Advanced documentation for specific RL libraries (e.g., `stable-baselines3`, `RLlib`)
- [ ] Academic literature on climate-adaptive design, urban microclimates, and building resilience
- [ ] Resources on whole-life carbon assessment methodologies (e.g., RICS guidance, academic papers)
- [ ] Case studies and research on co-simulation and human-AI interaction in design

### 🧪 Mini-Projects & Exercises
- [ ] Publish 3+ completed research components or mini-projects with clear documentation on GitHub
- [ ] Demonstrate effective version control with feature branches, pull requests, and code reviews
- [ ] Deploy a cloud-based energy simulation or ML inference demo as a proof-of-concept
- [ ] Create an **XAI demo** explaining a building energy prediction model's outputs (e.g., using SHAP)
- [ ] Implement a **more complex RL agent** for a multi-objective design optimization task
- [ ] Prototype a user-in-the-loop design interface integrating ML insights and simulation feedback
- [ ] Develop a conceptual framework or initial script for integrating a specific climate adaptation strategy into the generative design
- [ ] Research and outline a methodology for integrating whole-life carbon footprint prediction into the design workflow

---

## 📌 Optional / Stretch Goals

These are additional high-impact goals to pursue if time and opportunity allow, further enhancing your expertise:

- [ ] Develop a post-occupancy monitoring dashboard integrated with ML models for real-time performance insights.
- [ ] Conduct a detailed research project specifically on the implementation of a whole-life carbon footprint prediction model using ML.
- [ ] Actively contribute to an existing open-source project related to architectural simulation, generative design, or energy modeling.
- [ ] Attend and present at relevant academic conferences or workshops on ML in architecture and energy modeling.
- [ ] Explore advanced topics such as federated learning for data privacy or causal inference in building performance analysis.

---

## 🧭 Usage

- [ ] Mark tasks `[x]` when complete
- [ ] Add dates or notes to each task as needed (e.g., `[x] 2025-07-07: Completed EPW parser, see notebooks/01_data_visualisation.ipynb`)
- [ ] Use this checklist to track granular progress toward PhD readiness and guide daily/weekly learning.

