# Detailed Project Guide for PhD Readiness Roadmap  
*Foundations for Integrated ML, Generative Design & Energy Simulation for Climate-Adapted Net-Zero Buildings

---

## Phase 1 – Foundations: Python, Data Handling & Architectural File Parsing

### Learning Outcomes
- Develop strong Python programming fundamentals.
- Master data parsing, cleaning, and visualization using real-world architectural and climate datasets.
- Understand common file formats used in building simulation (EPW, CSV, JSON, IDF).
- Gain skills in exploratory data analysis and data-driven storytelling.

### Research Context
These foundational skills underpin your ability to preprocess climate and building data, critical for accurate energy simulation and ML model inputs. Handling real datasets early builds fluency for later integration with generative design and simulation tools.

### Recommended Reading
- *Python Crash Course* by Eric Matthes (Chapters 1-10) — solid intro to Python programming  
- *Automate the Boring Stuff with Python* by Al Sweigart — practical scripting and data handling  
- *Python for Data Analysis* by Wes McKinney (Chapters on pandas, data cleaning, and visualization)  
- EnergyPlus Weather File Format Documentation (official website)  
- EnergyPlus and OpenStudio User Manuals (sections on file formats and simulation inputs)  
- *Data Science from Scratch* by Joel Grus (Intro chapters) — for foundational data science concepts  
- Official pandas and matplotlib documentation (focus on data manipulation and plotting)

### Projects
1. **Parse and Visualize EPW Weather Files**  
2. **Visualize EnergyPlus CSV Outputs**  
3. **Parse and Explore OpenStudio/IDF Files**  
4. **Handle Parametric Geometry Data in JSON/CSV**

### Milestones & Assessments
- Deliver fully functional scripts with documentation.
- Produce visualizations demonstrating correct data interpretation.
- Self-review or peer code review focusing on readability and correctness.
- Test data parsers on multiple sample files to ensure robustness.

---

## Phase 2 – Machine Learning for Energy Prediction

### Learning Outcomes
- Build predictive models for building energy performance.
- Implement regression and classification algorithms relevant to architectural data.
- Evaluate model accuracy and optimize hyperparameters.
- Prepare datasets for ML workflows and apply feature engineering.

### Research Context
These ML skills support surrogate modeling, reducing simulation runtimes while maintaining accuracy. Effective ML prediction models are central to integrating simulation and generative design.

### Recommended Reading
- *Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow* by Aurélien Géron (Chapters 1-7) — solid ML fundamentals and regression models  
- *Interpretable Machine Learning* by Christoph Molnar — especially chapters on SHAP and LIME explainability techniques  
- *Feature Engineering for Machine Learning* by Alice Zheng and Amanda Casari — techniques to prepare building energy datasets  
- Scikit-learn official documentation (regression, classification, hyperparameter tuning)  
- Research articles on ML surrogate modeling in building energy simulation (e.g., papers by Ahmad et al., or recent surveys)  
- Intro tutorials on explainable AI frameworks SHAP and LIME (official repos and blogs)

### Projects
1. **Train ML Models on EPW + EnergyPlus Outputs**  
2. **Predict Building Energy Demand from Parametric Inputs**  
3. **Automate Model Evaluation and Hyperparameter Tuning**

### Milestones & Assessments
- Document ML pipeline from data preprocessing to evaluation.
- Compare multiple ML algorithms on benchmark datasets.
- Use visualization tools to interpret model predictions.
- Validate models on unseen or real building data.

---

## Phase 3 – ML-Integrated Generative Design

### Learning Outcomes
- Connect ML models with parametric design environments (e.g., Grasshopper).
- Implement real-time feedback loops for generative optimization.
- Develop scripts/components to automate design evaluation and iteration.
- Understand multi-objective optimization principles.

### Research Context
This phase embodies the core of your PhD research—linking generative design with ML-driven energy performance prediction, enabling rapid, informed architectural design iterations.

### Recommended Reading
- *Reinforcement Learning: An Introduction* by Sutton and Barto (Chapters 1-6) — foundational RL theory  
- *Hands-On Reinforcement Learning with Python* by Sudharsan Ravichandiran (selected chapters on policy gradients and Q-learning)  
- *Generative Design* by William J. Mitchell (for architectural design context)  
- Rhino and Grasshopper official tutorials (with focus on Ladybug Tools integration)  
- Research papers on RL applications in architectural and parametric design  
- Tutorials on integrating ML models with Grasshopper (online courses, GitHub repos)

### Projects
1. **Integrate ML Energy Models into Grasshopper Workflows**  
2. **Develop Generative Design Algorithms with ML Feedback**  
3. **Implement Multi-Objective Optimization Frameworks**

### Milestones & Assessments
- Demonstrate working generative design workflows with ML feedback.
- Present case studies with design alternatives and energy predictions.
- Evaluate optimization results and document trade-offs.
- Prepare tutorials or demos for peer sharing.

---

## Phase 4 – Simulation-ML Feedback Loops and Automation

### Learning Outcomes
- Automate full simulation workflows linking EnergyPlus/OpenStudio with ML models.
- Implement retraining pipelines based on new simulation results.
- Optimize design solutions using combined simulation and ML surrogate models.
- Develop user-in-the-loop or designer-in-the-loop frameworks.

### Research Context
This phase ensures that your research includes realistic iterative workflows, where simulations guide ML model updates and design optimization, reflecting true architectural practice and academic innovation.

### Recommended Reading
- EnergyPlus and OpenStudio API documentation and scripting guides  
- *Python Scripting for Computational Science* by Hans Petter Langtangen (for automation workflows)  
- Papers and case studies on iterative simulation and ML retraining workflows  
- Tutorials on combining ML surrogate models with simulation (e.g., on GitHub or Medium blogs)  
- Reinforcement learning advanced topics for control and automation (relevant chapters from Sutton & Barto)  
- Documentation for workflow orchestration tools (e.g., Apache Airflow or Prefect, if applicable)

### Projects
1. **Create Simulation Automation Pipelines**  
2. **Develop ML Model Retraining and Validation Scripts**  
3. **Build Optimization Algorithms Combining Simulation & ML**

### Milestones & Assessments
- Produce end-to-end scripts automating simulation and retraining.
- Validate iterative improvements in prediction accuracy and design quality.
- Document workflows with diagrams and explanations.
- Test frameworks on multiple design scenarios.

---

## Phase 5 – Portfolio & Advanced Research Integration

### Learning Outcomes
- Consolidate project outputs into a professional portfolio.
- Present research contributions clearly and compellingly.
- Prepare for PhD proposal defenses and academic publication.
- Explore extensions such as explainable AI, climate-adapted design, and whole-life carbon modeling.

### Research Context
This final phase focuses on communicating your readiness for PhD research, showing mastery over integrated ML-generative design-energy simulation workflows aligned with Net Zero and climate adaptation goals.

### Recommended Reading
- *The Craft of Research* by Booth, Colomb, and Williams — for academic writing and presenting research  
- Selected journal articles on climate-adaptive generative design and whole-life carbon modeling  
- Tutorials on creating effective portfolios and project documentation (GitHub guides)  
- Papers on post-occupancy evaluation and calibration of building models  
- Guides on explainable AI applications in architecture and sustainability  
- Resources on academic publishing, proposal writing, and conference presentations

### Projects
1. **Prepare Online Portfolio Showcasing Projects**  
2. **Develop Case Studies on Climate-Adaptive Generative Design**  
3. **Investigate Explainable AI for Model Transparency**  
4. **Explore Whole-Life Carbon and Post-Occupancy Calibration**

### Milestones & Assessments
- Complete a polished portfolio website with project summaries and code.
- Write reflective reports linking projects to PhD aims.
- Present work to peers or advisors for feedback.
- Identify gaps and plan next research steps.

---

# General Recommendations

- **Regular Checkpoints:** Schedule biweekly or monthly reviews to assess progress, adjust goals, and incorporate feedback.
- **Documentation:** Keep clear, detailed notes and comments to facilitate knowledge transfer and future publication.
- **Version Control:** Use GitHub repositories with clear commit messages and issue tracking.
- **Community Engagement:** Share progress in relevant online forums or with academic peers to gain insights and collaboration opportunities.
- **Backup & Data Management:** Regularly back up datasets, models, and scripts to avoid data loss.

---

