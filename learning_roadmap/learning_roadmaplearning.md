# 🎓 PhD Readiness Roadmap: ML + Generative Design + Energy Simulation

This roadmap outlines a progressive learning and project plan to prepare for a PhD in integrating machine learning, generative design, and energy simulation in architecture. It emphasizes practical skills, tool proficiency, and research rigor across 12+ months.

---

## 📑 Table of Contents
- [Phase 1: Foundations (0–3 months)](#phase-1-foundations-03-months)
- [Phase 2: ML for Energy Prediction (3–6 months)](#phase-2-ml-for-energy-prediction-36-months)
- [Phase 3: Generative Design + Optimization (6–9 months)](#phase-3-generative-design--multi-objective-optimization-69-months)
- [Phase 4: Simulation & Feedback Loop (9–12 months)](#phase-4-simulation--feedback-loop-912-months)
- [Phase 5: Research Portfolio (12+ months)](#phase-5-research-portfolio--scientific-readiness-12-months)
- [Integrated Topics](#integrated-topics-advanced-research-skills)
- [Suggested Timeline](#suggested-timeline)

---

## 🧱 Phase 1: Foundations (0–3 months)

**🎯 Goal:** Develop fluency in Python, data workflows, and energy modeling basics.
🏷️ `#python` `#energy-simulation` `#ifc` `#data-handling`

### 🔑 Core Skills & Tools
- Python Programming: Variables, loops, functions, file I/O
- Data Science Libraries: `pandas`, `numpy`, `matplotlib`, `seaborn`
- File Formats: CSV, JSON, IDF, EPW, IFC, gbXML
- Energy Modeling Concepts:
  - Passivhaus and Net Zero design principles
  - EnergyPlus and OpenStudio overview
- BIM Interoperability: Revit → IFC extraction (via Dynamo scripts)

> 💡 **Why It Matters:**  
> These are the minimum foundations to enable automation of simulation workflows and handle building metadata across formats.

### 📘 Key Resources  

#### Books (selected chapters)  
- **Python for Data Analysis** by Wes McKinney  
  - Chapter 1: “Preliminary: Python Language Basics, IPython, and Jupyter Notebooks”  
  - Chapter 3: “Built-in Data Structures, Functions, and Files”  
  - Chapter 5: “Getting Started with pandas”  
- **Energy Simulation in Building Design** by Joseph Clarke  
  - Chapter 2: “Introduction to EnergyPlus Simulation Engine”  
  - Chapter 4: “Input Data and Weather Files”  

#### Online Resources  
- [Official Python Tutorial](https://docs.python.org/3/tutorial/)  
- [EnergyPlus Documentation & Engineering Reference](https://energyplus.net/documentation)  
- [Ladybug Tools Tutorials](https://www.ladybug.tools/tutorials.html)  
- [IFC File Format Overview](https://technical.buildingsmart.org/standards/ifc/)  
- [Dynamo BIM Tutorials](https://dynamobim.org/learn/)  

### 🧪 Mini-Projects & Exercises
- [ ] Create a **weather data parser** that extracts and processes data from EPW files.  ⏱ ~3h  
- [ ] Build a **CSV data visualizer** to plot and explore simple energy or climate datasets.  ⏱ ~2h  
- [ ] Experiment with file handling: Read/write JSON, CSV, and explore IDF template files. ⏱ ~4h
- [ ] Practice Python basics: control flow, functions, and I/O.

---

## 🧠 Phase 2: ML for Energy Prediction (3–6 months)

**🎯 Goal:** Apply ML to predict building performance from parametric and climate data.
🏷️ `#ml` `#energy-prediction` `#xai` `#surrogate-modeling`

### 🔑 Skills to Learn
- Regression & Ensemble Models: Linear Regression, Random Forest, XGBoost
- Neural Networks: TensorFlow/Keras basics for MLPs
- Data Handling: One-hot encoding, feature scaling, PCA
- Evaluation Metrics: MAE, RMSE, R²
- Explainable AI (XAI) basics: feature importance, SHAP   values

> 💡 **Why It Matters:**  
> Feature importance (e.g., SHAP) helps translate ML insights into architectural decisions—essential for explainability in generative design workflows.

### 🛠 Tools
- `scikit-learn`, `tensorflow`, `shap`, `matplotlib`, `seaborn`

### 📘 Key Resources  

#### Books (selected chapters)  
- **Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow** by Aurélien Géron  
  - Chapter 2: “End-to-End Machine Learning Project”  
  - Chapter 3: “Classification” (focus on regression methods)  
  - Chapter 5: “Training Deep Neural Nets” (basic concepts)  
- **Interpretable Machine Learning** by Christoph Molnar (free online)  
  - Chapter 2: “Global Surrogate Models”  
  - Chapter 4: “SHAP Values”  
  - Online book: [https://christophm.github.io/interpretable-ml-book/](https://christophm.github.io/interpretable-ml-book/)  

#### Online Resources  
- [Scikit-learn User Guide](https://scikit-learn.org/stable/user_guide.html)  
- [TensorFlow Tutorials](https://www.tensorflow.org/tutorials)  
- [SHAP Documentation and Examples](https://shap.readthedocs.io/en/latest/)  
- Streamlit [Getting Started](https://docs.streamlit.io/library/get-started)  

### 🧪 Mini-Projects & Exercises
- [ ] Train a **regression model** to predict heating and cooling loads using simulated or real datasets.  ⏱ ~4h 
- [ ] Implement **model comparison** across Linear Regression, Random Forest, and XGBoost to evaluate performance differences.  ⏱ ~3h 
- [ ] Create a **simple dashboard** (using Streamlit or Dash) to visualize Energy Use Intensity (EUI) predictions interactively. ⏱ ~5h

---

## 🔁 Phase 3: Generative Design + Multi-Objective Optimization (6–9 months)

**🎯 Goal:** Automate design evolution based on ML feedback.
🏷️ `#generative-design` `#multi-objective` `#evolutionary-algorithms` `#energy+daylight`

### 🔑 Skills to Learn
- Genetic Algorithms: NSGA-II, `DEAP`, `Platypus`
- Design Encoding: Parametric models, genotype representation
- Fitness Functions: Combine EUI, DA, UDI, PMV, embodied carbon
- Multi-Criteria Visualization: Parallel coordinate plots, Pareto analysis
- User-in-the-Loop Design: Preference learning, UX for human override

> 💡 **Why It Matters:**  
> Generative design enables systematic exploration of trade-offs in energy vs comfort vs carbon—beyond what static design allows.

### 🛠 Tools
- Rhino + Grasshopper + Ladybug/Honeybee
- `DEAP`, `Platypus`, `Wallacei`, `Octopus`
- `Streamlit`/`Dash` for basic UI prototyping

### 📘 Key Resources  

#### Books (selected chapters)  
- **Evolutionary Computation for Modeling and Optimization** by Daniel Ashlock  
  - Chapter 3: “Genetic Algorithms”  
  - Chapter 7: “Multiobjective Optimization”  
- **Multi-Objective Optimization Using Evolutionary Algorithms** by Kalyanmoy Deb  
  - Chapter 1: “Introduction”  
  - Chapter 3: “Non-dominated Sorting Genetic Algorithm (NSGA-II)”  
- Ladybug Tools official tutorials on parametric optimization:  
  - [https://www.ladybug.tools/](https://www.ladybug.tools/)  

#### Online Resources  
- [DEAP Documentation](https://deap.readthedocs.io/en/master/)  
- [Platypus Optimization Framework](https://platypus.readthedocs.io/en/latest/)  
- Wallacei plugin tutorials: [https://www.wallacei.com/](https://www.wallacei.com/)  
- Parallel coordinate plots with `plotly`: [https://plotly.com/python/parallel-coordinates-plot/](https://plotly.com/python/parallel-coordinates-plot/)  

### 🧪 Mini-Projects & Exercises
- [ ] Code a **simple grid-based layout generator** using random sampling techniques.  ⏱ ~6h 
- [ ] Develop a **basic genetic algorithm** for floor plan optimization based on multiple objectives like energy and daylight metrics.  ⏱ ~3h 
- [ ] Visualize multi-objective optimization results with **parallel coordinate plots** or Pareto front charts. ⏱ ~4h

---

## 🔬 Phase 4: Simulation & Feedback Loop (9–12 months)

**🎯 Goal:** Automate simulations, feed results to ML, refine designs.
🏷️ `#simulation` `#openstudio` `#uncertainty` `#feedback-loop`

### 🔑 Skills to Learn
- Python APIs: `eppy`, `geomeppy`, OpenStudio CLI
- Simulation Automation: Batch runs, parameter sweeping
- Weather + Occupancy Modeling: EPW integration, stochastic modeling
- Uncertainty Quantification: Monte Carlo sampling, `SALib`

> 💡 **Why It Matters:**  
> Closing the loop between simulation and ML enables smarter generative workflows with faster feedback for designers.

### 🛠 Tools
- EnergyPlus, OpenStudio, Ladybug Tools, SimTool, URBANopt
- Streamlit UI for real-time update of performance metrics

### 📘 Key Resources  

#### Books (selected chapters)  
- **Building Performance Simulation for Design and Operation** by Jan L.M. Hensen and Roberto Lamberts  
  - Chapter 6: “Simulation Automation and Optimization”  
  - Chapter 8: “Uncertainty and Sensitivity Analysis”  
- EnergyPlus Engineering Reference  
  - Chapters on API usage and scripting automation  

#### Online Resources  
- [Eppy Documentation](https://eppy.readthedocs.io/en/latest/)  
- [Geomeppy GitHub](https://github.com/jdselbo/geomeppy)  
- [OpenStudio SDK Documentation](https://openstudio.net/developer)  
- [SALib Sensitivity Analysis Library](https://salib.readthedocs.io/en/latest/)  

### 🧪 Mini-Projects & Exercises
- [ ] Automate **EnergyPlus simulation runs** via Python using `eppy` or OpenStudio API.  ⏱ ~4h  
- [ ] Run **multiple design iterations** automatically, logging energy usage and performance outputs for analysis.  ⏱ ~3h 
- [ ] Integrate stochastic **occupancy and weather data** into simulations to model real-world variability.  ⏱ ~5h

---

## 💻 Phase 5: Research Portfolio & Scientific Readiness (12+ months)

**🎯 Goal:** Develop reproducible workflows and demonstrate scientific rigor through documentation and open-source code.
🏷️ `#reproducibility` `#validation` `#github` `#scientific-method`

### 🔑 Skills to Learn  
- Scientific writing and documentation best practices  
- Version control with Git and GitHub workflows  
- Experiment tracking (MLflow, Weights & Biases)  
- Post-occupancy calibration and validation metrics (CVRMSE, NMBE)  
- Designing control and ablation studies  

> 💡 **Why It Matters:**  
> Scientific reproducibility is critical for PhD proposals and publications—structured workflows with documented metrics are a must.

### 📘 Key Resources  

#### Books & Articles  
- **The Craft of Research** by Booth, Colomb, and Williams  
  - Chapters on argumentation, evidence, and reporting research  
- **Git Pro Book** (free online)  
  - Chapter on branching and collaboration: [https://git-scm.com/book/en/v2](https://git-scm.com/book/en/v2)  
- MLflow Documentation: [https://mlflow.org/docs/latest/index.html](https://mlflow.org/docs/latest/index.html)  
- [ASHRAE Guideline 14-2014: Measurement of Energy and Demand Savings](https://www.ashrae.org/technical-resources/standards-and-guidelines/standards-addenda)  

### 🧪 Mini-Projects & Exercises  
- [ ] Set up a GitHub repo with code, data, and Jupyter notebooks documenting the full pipeline.  ⏱ ~4h  
- [ ] Write detailed tutorials/blog posts explaining your methodology.  ⏱ ~6h 
- [ ] Track experiments with MLflow or Weights & Biases, including metadata and metrics.  
- [ ] Prepare validation reports comparing simulation predictions with post-occupancy data.  

---

## 📦 Integrated Topics: Where to Add Advanced Research Skills

| Advanced Topic                     | Integration Phase     | Learning Goals                                    | Tools                              |
|----------------------------------|------------------------|---------------------------------------------------|------------------------------------|
| Post-Occupancy Calibration       | Phase 4 & 5            | Align predictions with real performance          | OpenStudio Measures, PyBEM, Pandas |
| Embodied/Whole Life Carbon       | Phase 3 & 4            | Calculate carbon from material data              | OneClick LCA, EC3, IFC + GH        |
| Multi-Objective Optimization     | Phase 3                | NSGA-II with Pareto visualizations               | DEAP, Platypus, Wallacei           |
| Explainable AI for Architects    | Phase 2 & 3            | Visual feedback from ML models                   | SHAP, Streamlit                    |
| Co-Simulation (Lighting, Airflow)| Phase 4+               | EnergyPlus + Radiance/CFD integration            | Honeybee, OpenFOAM, URBANopt       |
| Designer-in-the-Loop Optimization| Phase 3 & 5            | Real-time feedback and manual override           | Dash, preference learning models   |
| Scientific Rigor & Validation    | Phase 5                | Experimental design, metrics, reproducibility    | MLflow, Git, Jupyter               |
| Cloud Computing & Scalability    | Phase 4 & 5            | Parallel simulations and ML training             | AWS, Colab Pro, Prefect, Docker    |

---

## 📚 Suggested Timeline (Gantt-like Summary)

| Months  | Focus Area                     | Key Outcome                                        |
|---------|--------------------------------|----------------------------------------------------|
| 0–3     | Python + Data + Energy Modeling| First parametric models + energy simulations       |
| 3–6     | ML for Energy Prediction       | Regression model + validation plots                |
| 6–9     | Generative Design + Optimization| Evolving layouts based on ML + simulation          |
| 9–12    | Feedback Loop + XAI + Validation| Automated loop + explainability visualizations     |
| 12+     | Portfolio + Research Presentation| Documented GitHub + UI + full pipeline ready       |
