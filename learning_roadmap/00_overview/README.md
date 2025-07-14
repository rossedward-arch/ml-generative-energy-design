# PhD Readiness Project Guide: Foundations for Integrated ML, Generative Design & Energy Simulation for Climate-Adapted Net-Zero Buildings

---

## 🧱 Phase 1: Foundations (0–3 months)

**Goal:** Develop fluency in Python programming, data workflows, and fundamental energy modeling concepts.

### Core Skills & Tools
- Python basics: variables, control flow, functions, file I/O  
- Data manipulation: pandas, numpy  
- Data visualization: matplotlib, seaborn  
- Working with climate data (e.g. UKCP18, EPW files)  
- Energy modeling basics: Passivhaus principles, EnergyPlus overview  
- BIM data extraction: IFC parsing  
- Version control basics: Git and GitHub  

### Mini-Projects
- EPW weather file parser and summary tool  
- CSV data visualizer with temperature, humidity, solar radiation plots  
- UKCP18 climate scenario explorer (extract & plot local temperature change trends)  
- Simple Python scripts with Git version control  

### Recommended Reading
- *Python for Data Analysis* (Wes McKinney) – selected chapters on pandas and numpy  
- *Energy Simulation in Building Design* (Joseph Clarke) – introductory chapters

---

## ⚙️ Phase 2: Machine Learning for Energy Prediction (3–6 months)

**Goal:** Learn supervised ML methods to predict building energy performance.

### Core Skills & Tools
- Supervised learning: linear regression, decision trees, random forests  
- Model evaluation metrics: MAE, RMSE, R², cross-validation  
- Feature engineering and selection  
- Data pipelines and cleaning (real simulation/climate datasets)  
- Tools: scikit-learn, Jupyter notebooks  

### Mini-Projects
- Predict annual heating load using building parameters  
- Compare ML models (baseline vs tuned) for energy use prediction  
- Plot evaluation metrics and explain model strengths/weaknesses  
- Test basic SHAP values on a trained random forest  

### Recommended Reading
- *Introduction to Machine Learning with Python* (Andreas C. Müller) – regression, validation  
- Research papers on ML for building energy prediction

---

## 🕹️ Phase 3: ML-Integrated Generative Design (6–12 months)

**Goal:** Integrate ML models with parametric generative design workflows.

### Core Skills & Tools
- Parametric modeling: Grasshopper, Rhino  
- Surrogate modeling: training ML models to emulate simulation outputs  
- Optimization: genetic algorithms, Bayesian optimization  
- Visualization of iterations, convergence, design tradeoffs  

### Mini-Projects
- Parametric model optimizing window-to-wall ratio using ML surrogate  
- Surrogate vs brute-force optimization comparison  
- Visualize energy-performance Pareto front from design alternatives  

### Recommended Reading
- *Generative Design* (Benny B. Lau et al.) – selected chapters  
- Papers on surrogate-assisted optimization in architecture

---

## 🔄 Phase 4: Simulation-ML Feedback Loops (12–18 months)

**Goal:** Develop workflows combining building energy simulation and ML in iterative feedback loops.

### Core Skills & Tools
- Building simulation tools: EnergyPlus, OpenStudio, Ladybug/Honeybee  
- Automating simulation runs via parametric input scripts  
- Data extraction, cleaning, and ML re-training  
- Reinforcement learning basics (concepts + simple environments)  
- SHAP for simulation-driven model interpretation  

### Mini-Projects
- Automate EnergyPlus simulations across climate scenarios  
- Train a surrogate model from simulation results and analyze error  
- Implement iterative simulation–ML–optimization feedback loop  
- Run a basic reinforcement learning algorithm (OpenAI Gym: energy scheduling or comfort task)  

### Recommended Reading
- *Energy Simulation in Building Design* (Joseph Clarke) – advanced chapters  
- Papers on simulation-ML integration and RL in architecture  
- SHAP and XAI documentation (interpreting ML predictions for design insight)

---

## 🔬 Phase 5: Portfolio & Research Extensions (18+ months & Ongoing)

**Goal:** Deepen expertise in advanced ML, create portfolio-ready research components, and explore broader applications.

### Core Skills & Tools
- Reinforcement learning (e.g. PPO, SAC)  
- Explainable AI (e.g. SHAP, LIME) applied to energy models  
- Climate adaptation strategies (passive design, overheating resilience)  
- Whole-life carbon (WLC) assessment and integration into generative design  
- Advanced visualization: Plotly, Dash, Streamlit  
- Collaborative Git workflows and branching strategies  
- Cloud computing basics (e.g. Colab, AWS for simulation & ML)  
- Post-occupancy data integration and model calibration  

### Mini-Projects
- Use SHAP to interpret design tradeoffs in a generative process  
- Build an interactive dashboard for visualizing design iterations  
- Prototype climate-adaptive strategies (e.g., shading or massing) under UKCP18 data  
- Integrate early-stage WLC estimates in a design optimization loop  

### Recommended Reading
- Research papers on RL in architectural workflows  
- XAI literature and use cases in sustainability  
- Articles on climate-resilient design and WLC workflows  
- Advanced tool documentation (e.g. SHAP, LIME, `stable-baselines3`)  

---

## 📅 Summary Timeline

| Phase                         | Duration        | Core Focus                                      |
|-------------------------------|-----------------|-------------------------------------------------|
| Phase 1: Foundations          | 0–3 months      | Python, data workflows, climate & modeling      |
| Phase 2: ML Prediction        | 3–6 months      | Supervised learning, model evaluation           |
| Phase 3: Generative Design    | 6–12 months     | Parametric design + surrogate models            |
| Phase 4: Simulation Loop      | 12–18 months    | Simulation + ML feedback + SHAP/RL foundations  |
| Phase 5: Portfolio & Extensions | 18+ months      | XAI, climate adaptation, WLC, visualization     |

---

*This roadmap is a structured, evolving guide for developing PhD-level research capabilities in machine learning, generative design, and energy simulation for climate-adapted, net-zero architecture. It balances theoretical depth with practical application across tools and methods essential for CDT success.*


