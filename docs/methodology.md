# Methodology

## 1. Research Approach

This methodology extends prior ML–generative design frameworks by embedding Passivhaus and Net Zero principles early in the conceptual design phase, prioritizing energy performance and comfort metrics through an iterative, data-driven feedback loop. Unlike previous approaches, this integration emphasizes automation at the early-stage decision-making level and is tailored to high-performance architectural targets. The approach supports architectural decisions targeting Passivhaus certification and Net Zero energy performance by integrating performance prediction with design exploration. This research addresses a critical gap by unifying early-stage generative design with continuous ML-predicted energy feedback, targeting Passivhaus/Net Zero compliance at pre-schematic phases—an integration not extensively realized in current architectural design pipelines.

- **Predictive Modeling:** Machine learning techniques predict building energy use and occupant comfort based on early design parameters such as geometry, orientation, and materials (Ascione et al., 2017; Goodfellow et al., 2016).  
- **Generative Optimization:** Genetic algorithms iteratively explore the design space to optimize layouts for energy efficiency and comfort, guided by simulation feedback and ML predictions (Mitchell, 1998; Bendsøe & Sigmund, 2003).  
- The integration of Passivhaus principles (airtightness, insulation, ventilation) and Net Zero targets provides a robust framework ensuring designs meet stringent energy and sustainability goals (Passivhaus Trust, 2024; UK Government, 2021).

---

## 2. Data Sources & Processing

The project utilizes diverse datasets to support machine learning and energy simulation tasks:

- **Building Geometry and Design Parameters:** CAD/BIM exports (e.g., Revit) providing spatial layouts, dimensions, and material specifications (Eastman et al., 2018; Revit, 2023).  
- **Weather Data:** Typical meteorological year files (EPW format) for site-specific climate conditions (EnergyPlus Weather Data, 2024).  
- **Energy Simulation Outputs:** EnergyPlus or OpenStudio results capturing energy use intensity (EUI), thermal comfort metrics, HVAC loads, etc. (Crawley et al., 2008).  
- **Performance Benchmarks:** Passivhaus certification criteria and Net Zero energy targets for reference and validation (Passivhaus Trust, 2024; UK Government, 2021).  

> The majority of data is tabular or spatial-temporal, with formats including CSV, JSON, and IDF.  
> Datasets are organized into reproducible data pipelines ensuring consistency across simulations and training workflows.

> Geometric data from BIM platforms (e.g., Revit) is translated into simulation-ready inputs via IFC parsers or custom Dynamo scripts that extract and structure relevant attributes (e.g., surface areas, zoning, materials) for integration with EnergyPlus-compatible IDF files.

> To address variability in design and climate conditions, uncertainty in inputs—such as occupancy schedules and weather profiles—is handled using stochastic sampling or Monte Carlo simulation, enabling more robust performance predictions across probabilistic design scenarios.

---
### 🔄 Data Flow Diagram

```mermaid
flowchart TD
    A["Building Geometry\n(BIM / Revit / IFC)"] --> B["Feature Extraction"]
    B --> C["Simulation Configuration\n(IDF / OpenStudio)"]
    C --> D["Energy Simulation\n(EnergyPlus)"]

    E["Climate & Weather Data\n(EPW files)"] --> B
    F["Performance Benchmarks\n(Passivhaus / Net Zero)"] --> C

    D --> G["Simulation Results\n(CSV / SQLite)"]
    B --> H["ML-ready Features\n(CSV / Parquet)"]

    G --> I["Model Training\n(ML Algorithms)"]
    H --> I

    I --> J["Energy Performance Predictions\n(EUI, Comfort, Loads)"]

    style A fill:#e6f7ff,stroke:#3399cc
    style E fill:#e6f7ff,stroke:#3399cc
    style F fill:#e6f7ff,stroke:#3399cc
    style B fill:#fff2cc,stroke:#e69138
    style C fill:#fff2cc,stroke:#e69138
    style D fill:#fde9d9,stroke:#d6604d
    style G fill:#f4cccc,stroke:#cc0000
    style H fill:#f4cccc,stroke:#cc0000
    style I fill:#d9ead3,stroke:#38761d
    style J fill:#d9ead3,stroke:#38761d

### Data Preprocessing and Feature Engineering

Effective preprocessing is critical to ensure model accuracy and interpretability:

- **Data Cleaning:** Handling missing values and correcting inconsistencies in geometry and simulation outputs (Kotsiantis et al., 2006).  
- **Normalization and Scaling:** Standardizing numerical features such as floor areas, orientations, and weather variables (Goodfellow et al., 2016).  
- **Feature Extraction:** Deriving relevant features like window-to-wall ratio, building compactness, solar exposure angles, and thermal mass indicators (Li et al., 2019).  
- **Categorical Encoding:** Converting categorical design variables (e.g., construction type, HVAC system) into numerical formats suitable for ML models (Zhang et al., 2020).  
- **Temporal Aggregation:** Summarizing hourly or daily weather or energy data into meaningful statistics (e.g., monthly averages, peak loads).  
- **Dimensionality Reduction:** Applying Principal Component Analysis (PCA) if feature space becomes large or highly correlated (Jolliffe & Cadima, 2016).  

---

### 📊 Data Flow Summary Table

| **Stage**          | **Type**                 | **Format**       | **Description**                                                               |
|--------------------|--------------------------|------------------|-------------------------------------------------------------------------------|
| **Input**          | Building Geometry        | JSON, DXF, IFC   | Parametric models or predefined layouts; includes floor area, WWR, zoning    |
|                    | Climate / Weather Data   | EPW              | Hourly weather profiles: temperature, radiation, humidity                    |
|                    | Construction Benchmarks  | CSV, JSON        | U-values, infiltration rates, HVAC presets from Passivhaus datasets          |
| **Transformation** | Feature Extraction       | Tabular          | Derives ratios, materials, orientations, envelope metrics                    |
|                    | Data Cleaning & Encoding | Tabular          | One-hot encoding for categories; normalization for numeric data              |
|                    | Simulation Configuration | IDF (EnergyPlus) | Translated inputs used for energy and comfort simulations                    |
| **Output**         | Simulation Results       | CSV, SQLite      | Outputs include EUI, daylight autonomy, overheating hours                    |
|                    | ML-ready Feature Sets    | CSV, Parquet     | Cleaned and structured datasets for training and evaluation                  |

---

## 3. Machine Learning Methods

- **Models:**  
  - Linear Regression and Random Forest for regression tasks (Breiman, 2001).  
  - Neural Networks using TensorFlow for complex energy prediction (Goodfellow et al., 2016).  

- **Model Selection Justification:**  
  - Linear models offer interpretability and straightforward insights.  
  - Random Forest captures nonlinear relationships and provides feature importance rankings.  
  - Neural Networks model complex multivariate energy and comfort patterns.

- **Learning Approaches:**  
  - Primarily supervised learning for energy use and comfort prediction.  
  - Future exploration of unsupervised learning (e.g., clustering for building typologies) and reinforcement learning for adaptive design (Sutton & Barto, 2018).

- **Training:**  
  - Data split into training, validation, and test sets.  
  - Hyperparameter tuning and cross-validation optimize model performance (Kohavi, 1995).

- **Evaluation Metrics:**  
  - Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), and R² score (Willmott & Matsuura, 2005).

- **Interpretability:**  
  - SHAP values and permutation feature importance enhance transparency for architectural decision-making (Lundberg & Lee, 2017).

- **Baselines for Evaluation:**  
  - Rule-of-thumb energy estimates and simulation-only predictions (from EnergyPlus or OpenStudio) will serve as performance baselines.  
  - These baselines provide reference points to measure model uplift and demonstrate value-added by ML approaches.

- **Ensemble Techniques:**  
  - Ensemble learning strategies (e.g., model stacking, weighted averaging) will be explored to improve predictive robustness and accuracy across heterogeneous building types and climates.

---

### 🔁 Model Lifecycle Diagram

```mermaid
flowchart TD
    A["Input Features\n(Design + Climate + Envelope)"] --> B["Model Training\n(Supervised Learning)"]
    B --> C["Validation\n(Cross-validation / Tuning)"]
    C --> D["Testing\n(Performance Metrics)"]
    D --> E["Energy & Comfort Predictions"]

    F["Baselines\n(Rule-of-thumb / Simulation-only)"] --> D
    G["Ensemble Models\n(Stacking / Averaging)"] --> E

    style A fill:#e6f7ff,stroke:#3399cc
    style B fill:#fff2cc,stroke:#e69138
    style C fill:#fde9d9,stroke:#d6604d
    style D fill:#f4cccc,stroke:#cc0000
    style E fill:#d9ead3,stroke:#38761d
    style F fill:#cfe2f3,stroke:#3d85c6
    style G fill:#c9daf8,stroke:#6d9eeb


## 4. Generative Design Workflow

- **Algorithm:** Genetic Algorithms implemented via the DEAP library (Fortin et al., 2012).  

- **Design Encoding:** Parameters represent building layouts, including room sizes, orientations, and spatial adjacencies (Mitchell, 1998).  
  - Layouts are parameterized using bounding boxes for spaces, adjacency matrices to enforce connectivity rules, and spline-based controls for envelope geometry adaptation.

- **Optimization:**  
  - Multi-objective GA balances trade-offs between energy use, daylight access, and thermal comfort.  
  - Trade-offs are managed using Pareto front exploration with NSGA-II, allowing a spectrum of optimal design solutions to be visualized and selected.  
  - Fitness functions are weighted to reflect Passivhaus and Net Zero performance criteria.  
  - Constraints ensure constructability, spatial logic, and compliance with user or regulatory requirements (Bendsøe & Sigmund, 2003).  
  - Iterative mutation, crossover, and selection evolve improved design solutions over successive generations.

- **Validation Loop:**  
  - Energy simulation outputs (e.g., EUI, comfort scores) are fed back into the GA loop, refining future generations based on performance metrics (Crawley et al., 2008).

---

### 🧬 Generative Design and Simulation Loop (Mermaid)

```mermaid
flowchart TD
    A["Initial Design Parameters\n(Bounding Boxes, Adjacency, Splines)"] --> B["Encoding into Genotype"]
    B --> C["Genetic Algorithm\n(Selection, Crossover, Mutation)"]
    C --> D["Candidate Layouts"]
    D --> E["Simulation & Evaluation\n(EnergyPlus / Daylight Tools)"]
    E --> F["Performance Metrics\n(EUI, Comfort, Daylight)"]
    F --> G["Fitness Scoring & Pareto Ranking\n(NSGA-II)"]
    G --> H["Next Generation Designs"]
    H --> C

    style A fill:#e0f7fa,stroke:#00acc1
    style B fill:#f1f8e9,stroke:#558b2f
    style C fill:#fff9c4,stroke:#fbc02d
    style D fill:#f0f4c3,stroke:#c0ca33
    style E fill:#e1bee7,stroke:#8e24aa
    style F fill:#ffccbc,stroke:#e64a19
    style G fill:#ffe082,stroke:#ff6f00
    style H fill:#c8e6c9,stroke:#43a047


## 5. Energy Simulation Integration

- Integration with EnergyPlus and OpenStudio validates ML predictions and assesses detailed energy performance (Crawley et al., 2008).  
- Simulation feedback informs generative algorithm fitness evaluation, guiding optimization toward realistic designs.  
- Simulation workflow is **partially automated**, allowing **designer-in-the-loop** refinement at key iterations for qualitative input.  
- **Simulation outputs are smoothed and aggregated** before retraining ML models to improve convergence and reduce noise.  
- Continuous linking of simulation results with ML retraining enhances prediction accuracy over time.  
- Parametric tools (Grasshopper + Ladybug Tools) facilitate seamless geometry and simulation data exchange (Roudsari et al., 2013).  
- Current simulations focus on operational energy and thermal comfort; future work includes **whole life carbon assessments**, integrating embodied carbon data for holistic sustainability (OneClick LCA, 2024; eTool, 2023).

> 📌 **Simulation Calibration Note:** To ensure real-world relevance, future iterations of this workflow will include post-occupancy validation using ASHRAE Guideline 14 calibration techniques (ASHRAE, 2014).

> ⚡ **Time-Saving Benefit:** Machine learning reduces the time required for each design iteration by over 90%, replacing slow simulation runs (~10–30 min per iteration) with real-time surrogate predictions (~<1 sec), enabling rapid exploration of larger design spaces.

> 📊 **Feedback Hierarchy:** ML models predict multiple performance metrics—EUI, thermal comfort hours, daylight autonomy, and CO₂ concentration. Each metric is assigned a weight within the fitness function, reflecting project-specific priorities (e.g., EUI 0.4, comfort 0.3, daylight 0.2, CO₂ 0.1). This composite score informs the genetic algorithm during design selection.

---

### 🔄 Energy Simulation Workflow Diagram (Mermaid)

```mermaid
graph TD
    A["Parametric Geometry Definition\n(Grasshopper + Ladybug)"] --> B["Simulation Input Generation\n(IDF/JSON)"]
    B --> C["Energy Simulation\n(EnergyPlus / OpenStudio)"]
    C --> D["Raw Simulation Output"]
    D --> E["Output Processing\n(Smoothing & Aggregation)"]
    E --> F["ML Model Retraining\n(Prediction Refinement)"]
    F --> G["Generative Design Feedback Loop\n(Fitness Evaluation)"]
    G --> H{"Designer-In-The-Loop?"}
    H -- Yes --> I["Manual Design Adjustment"]
    H -- No --> J["Automated Next Iteration"]
    I --> A
    J --> A

    style A fill:#f0f8ff,stroke:#4682b4
    style B fill:#e6f7ff,stroke:#66afe9
    style C fill:#fde9d9,stroke:#d6604d
    style D fill:#fbe9e7,stroke:#ef6c00
    style E fill:#fff8dc,stroke:#e6ac00
    style F fill:#e1f5fe,stroke:#0288d1
    style G fill:#dcedc8,stroke:#7cb342
    style H fill:#ffe0b2,stroke:#f57c00
    style I fill:#f3e5f5,stroke:#9c27b0
    style J fill:#e8f5e9,stroke:#43a047


## 6. Software Tools & Environment

This research leverages an integrated stack of tools for data processing, modeling, simulation, and visualization to ensure replicability, modularity, and performance consistency.  
The system is designed in **modular stages** (data ingestion, modeling, optimization, simulation) to enable individual updates and testing.

---

### Python Libraries

Used for core data handling and modeling workflows:

- **Pandas**, **NumPy** – data wrangling and transformation  
- **Scikit-learn**, **TensorFlow** – machine learning and neural network modeling  
- **DEAP** – genetic algorithm-based generative optimization  

---

### Parametric Modeling

- **Grasshopper** and **Ladybug Tools** – rule-based visual scripting and environmental analysis  
- Enable flexible geometric parameterization and climate-informed design exploration  

---

### BIM Data Extraction

- **Revit** – exporting geometry and material metadata for downstream simulation and feature generation  
  *(Eastman et al., 2018; Revit, 2023)*  

---

### Energy Simulation Engines

- **EnergyPlus**, **OpenStudio** – used to validate ML predictions and evaluate compliance with Passivhaus and Net Zero standards  
  *(Crawley et al., 2008)*  
- Integrated via parametric runs and API hooks to allow seamless ML–simulation loops  

---

### Pipeline Orchestration

To manage multi-stage workflows (e.g., preprocessing → simulation → ML training), orchestration tools such as **Airflow**, **Luigi**, or **Prefect** can be integrated.  
These tools enable task scheduling, monitoring, and retry logic—key for scaling reproducible pipelines across compute clusters or cloud environments.

---

### Interactive User Interface

- **Streamlit** – rapid prototyping of web-based interfaces for real-time visualization, user interaction, and feedback collection  
  *(Streamlit Inc., 2023)*  
- Supports designer-in-the-loop optimization and decision-making  

---

### Environment Reproducibility

- Python environments managed with **Conda** for consistent dependency control  
- Containerization via **Docker** ensures platform-independent simulation workflows and replicable results across systems  

---

### Version Control

- Source code and simulation datasets tracked via **GitHub**  
- **Git LFS** (Large File Storage) used for handling IDF files, simulation logs, and model weights efficiently  

---

## 7. Challenges & Assumptions

This research involves several technical and practical challenges that influence the performance, validity, and generalizability of the proposed ML-assisted generative design workflow. Each limitation is addressed through mitigation strategies aligned with best practices in simulation science and machine learning.

### 🔍 Key Challenges and Mitigation Strategies

| **Challenge**                            | **Description**                                                                 | **Potential Mitigation**                                           | **Reference**                                                 |
|-----------------------------------------|---------------------------------------------------------------------------------|---------------------------------------------------------------------|---------------------------------------------------------------|
| **Data Limitations**                    | Scarcity of diverse, labeled building datasets across climates and types       | Use synthetic data, transfer learning, or expand data collection   | Kotsiantis et al., 2006                                       |
| **Model Simplifications**               | Behavioral and physical simplifications in simulation models                    | Incorporate stochastic models; validate with real-world data       | Andersen et al., 2014                                         |
| **Computational Cost**                  | High runtime from iterative simulations and optimization loops                  | Parallel computing; surrogate modeling; ML-accelerated workflows   | Zhao et al., 2017                                             |
| **Simulation Assumptions**              | Static weather or occupant assumptions may limit realism                        | Use dynamic schedules, stochastic weather sampling (Monte Carlo)   | Mahdavi & Tahmasebi, 2016                                     |
| **Prediction Gaps**                     | Early predictions often diverge from real post-occupancy performance            | Apply ASHRAE Guideline 14 calibration; post-occupancy feedback     | Mahdavi & Tahmasebi, 2016; ASHRAE, 2014                        |
| **Overfitting Risk**                    | ML models may overfit on small or unbalanced datasets                           | Use cross-validation, dropout, and regularization techniques        | Goodfellow et al., 2016                                       |
| **User Constraints**                    | Aesthetic, cost, and functional decisions may be missed by automated workflows  | Include manual review stages; designer-in-the-loop interventions   | Gerber et al., 2012                                           |
| **Domain Transferability**              | Model may underperform on unseen typologies or climates                         | Out-of-sample validation; ensemble models for broader generality   | Zhang et al., 2020                                            |

> Bias and Overfitting Risk: Since early-stage data may be sparse or imbalanced, overfitting remains a critical risk—especially with high-capacity models like neural networks. Techniques such as regularization, dropout, and k-fold cross-validation are employed to mitigate this.

> Realistic User Constraints: Design decisions in practice often depend on subjective criteria such as aesthetics, cost, or policy—which are difficult to encode into purely performance-based models. To account for this, the system supports **manual overrides** and **designer-in-the-loop feedback loops**.

> Simulation Calibration: Future validation will involve **post-occupancy evaluation** and **ASHRAE Guideline 14-compliant calibration** using real-world consumption data where available.

---

### 🧠 Challenge–Response Flowchart

```mermaid
flowchart TD
    A1["Data Limitations\nKotsiantis et al., 2006"] --> B1["Expand datasets or use transfer learning"]
    A2["Model Simplifications\nAndersen et al., 2014"] --> B2["Stochastic or hybrid models"]
    A3["Computational Cost\nZhao et al., 2017"] --> B3["Parallel/surrogate models"]
    A4["Simulation Assumptions\nMahdavi & Tahmasebi, 2016"] --> B4["Monte Carlo sampling"]
    A5["Prediction Gaps\nASHRAE, 2014"] --> B5["Post-occupancy calibration"]
    A6["Overfitting Risk\nGoodfellow et al., 2016"] --> B6["Regularization & cross-validation"]
    A7["User Constraints\nGerber et al., 2012"] --> B7["Designer-in-the-loop optimization"]
    A8["Domain Transferability\nZhang et al., 2020"] --> B8["Out-of-sample & ensemble testing"]

    style A1 fill:#f9f,stroke:#333
    style A2 fill:#f9f,stroke:#333
    style A3 fill:#f9f,stroke:#333
    style A4 fill:#f9f,stroke:#333
    style A5 fill:#f9f,stroke:#333
    style A6 fill:#f9f,stroke:#333
    style A7 fill:#f9f,stroke:#333
    style A8 fill:#f9f,stroke:#333
    style B1 fill:#d9fdd3,stroke:#333
    style B2 fill:#d9fdd3,stroke:#333
    style B3 fill:#d9fdd3,stroke:#333
    style B4 fill:#d9fdd3,stroke:#333
    style B5 fill:#d9fdd3,stroke:#333
    style B6 fill:#d9fdd3,stroke:#333
    style B7 fill:#d9fdd3,stroke:#333
    style B8 fill:#d9fdd3,stroke:#333


## 8. Future Work

This research opens several pathways for future development, ranging from short-term improvements to long-term architectural innovation and urban-scale impact.

### 🔹 Short-Term

- Expand the diversity and volume of training datasets across more building types, broader typologies, and diverse climatic zones.
- Enhance model interpretability using SHAP values and other explainable ML techniques (Lundberg & Lee, 2017).
- Conduct transferability tests on different design stages and building typologies.
- Incorporate occupant behavior modeling and adaptive control strategies to improve prediction realism (Andersen et al., 2014).
- Develop more intuitive, user-friendly interfaces for architects and designers.
- Include **human feedback incorporation** through interactive visual analytics and preference learning to steer generative outputs toward subjective or aesthetic goals.
- Create tutorials linked to each stage of the learning roadmap to support knowledge transfer and onboarding.

### 🔹 Medium-Term

- Integrate real-time sensor data (e.g., indoor temperature, CO₂ levels, occupancy) for live feedback loops.
- Develop hybrid workflows that combine measured and simulated data for adaptive design refinement.
- Incorporate **Whole Life Building Carbon Calculations** to assess both operational and embodied carbon impacts using tools such as OneClick LCA (OneClick LCA, 2024) or eTool (eTool, 2023).
- Enhance integration and automation between ML models, generative design algorithms, and energy simulation tools.
- Explore **co-simulation prospects** using tools like Radiance for daylighting, CFD (Computational Fluid Dynamics) for airflow and thermal comfort, and occupancy simulators to capture complex occupant–environment interactions.

### 🔹 Long-Term

- Build a full **Digital Twin framework** for post-occupancy monitoring, continuous learning, and predictive maintenance (Batty et al., 2012; Kritzinger et al., 2018).
- Enable ongoing model retraining based on real-world building performance and user behavior feedback.
- Integrate with city-scale energy and climate models for urban-scale generative design and planning.

```mermaid
flowchart TD
    A[Future Work]

    subgraph Short-Term
        direction TB
        ST1[Expand training datasets (types, climates)]
        ST2[Enhance interpretability (SHAP, explainable ML)]
        ST3[Transferability tests across design stages]
        ST4[Occupant behavior & adaptive control modeling]
        ST5[Develop intuitive user interfaces]
        ST6[Human feedback via visual analytics & preference learning]
        ST7[Tutorials for learning roadmap stages]
    end

    subgraph Medium-Term
        direction TB
        MT1[Real-time sensor data integration]
        MT2[Hybrid workflows: measured + simulated data]
        MT3[Whole Life Building Carbon Calculations (OneClick LCA, eTool)]
        MT4[Enhanced integration & automation of ML + generative + simulation]
        MT5[Co-simulation with Radiance, CFD, occupancy simulators]
    end

    subgraph Long-Term
        direction TB
        LT1[Digital Twin framework for monitoring & predictive maintenance]
        LT2[Ongoing model retraining from real-world data]
        LT3[City-scale integration for urban generative design & planning]
    end

    A --> Short-Term
    A --> Medium-Term
    A --> Long-Term


Future Work Roadmap
───────────────────────────────────────────────────────────────────
| Short-Term (0-1 year)      | Medium-Term (1-3 years)    | Long-Term (3+ years)       |
───────────────────────────────────────────────────────────────────
- Expand datasets           | - Real-time sensor data    | - Digital Twin framework
- Model interpretability   | - Hybrid workflows          | - Continuous retraining
- Transferability tests    | - Whole Life Carbon Calc.  | - Urban-scale integration
- Occupant modeling        | - Integration & automation | 
- User-friendly interfaces | - Co-simulation methods    | 
- Human feedback loops     |                            | 
- Learning tutorials       |                            |
───────────────────────────────────────────────────────────────────


---

## 9. Ethical & Sustainability Considerations

- Ensure data privacy and responsible use of simulation and machine learning data.  
- Promote energy-efficient and environmentally sustainable design outcomes.  
- Facilitate equitable access to tools supporting green building design.  
- **Data bias mitigation:** Include a diverse range of building typologies, with special attention to underserved regions to avoid bias and improve model fairness. Apply bias audits or reweighting techniques in training data (e.g., reweighting underrepresented building types or climates).  
- **Carbon awareness:** Ensure simulations incorporate both embodied carbon and grid energy sources, distinguishing renewable versus fossil-based energy impacts.  
- **Energy equity:** Address energy justice by designing solutions that support marginalized communities and promote inclusive sustainability.  
- **Sustainability evaluation framework:** Reference established tools such as the UN SDG framework or RIBA 2030 benchmarks as ethical guides for sustainability goals.

---

## 10. Interdisciplinary Collaboration

- Engage experts in architecture, engineering, computer science, and data science.  
- Encourage feedback from practicing architects and sustainability consultants.  
- Foster collaborative environments for co-development and knowledge sharing.  
- Engage in co-design workshops with architects and sustainability consultants to ensure practical relevance.  
- Use participatory modeling sessions to align ML-generated outcomes with real-world design values and stakeholder priorities.  
- **Academic/industry engagement mechanisms:** Knowledge co-creation will occur through workshops, interviews, and usability testing with practicing architects and energy consultants.

---

## 11. Documentation & Reporting

- Maintain clear records of data sources, code versions, and experimental results.  
- Transparently report model assumptions, limitations, and validation outcomes.  
- Use version control (Git) to track project development.  
- Adhere to FAIR data principles for dataset curation to ensure data is Findable, Accessible, Interoperable, and Reusable.  
- Use Jupyter Notebooks and Sphinx to document code, workflows, and model validation results for reproducibility and clarity.  
- **ML experiment tracking:** Incorporate tools like MLflow, Weights & Biases, or Comet.ml for experiment versioning, which is especially important for retraining loops.


---

## Methodology Workflow Diagram

```mermaid
flowchart TD
    %% Define styles for different categories
    classDef mlStep fill:#a2d2ff,stroke:#0b3d91,stroke-width:2px,color:#000
    classDef simStep fill:#ffb4a2,stroke:#9b2226,stroke-width:2px,color:#000
    classDef humanStep fill:#caffbf,stroke:#2d6a4f,stroke-width:2px,color:#000
    classDef defaultStep fill:#f0efeb,stroke:#666,stroke-width:1px,color:#000

    %% Main flowchart nodes
    A[Start: Define Research Objectives]:::defaultStep --> B[Collect & Prepare Data]:::defaultStep
    B --> C[Machine Learning Modeling]:::mlStep
    C --> D[Generative Design Optimization]:::mlStep
    D --> E[Energy Simulation Validation]:::simStep
    E --> F{Are Performance Criteria Met?}:::simStep

    F -- Yes --> G[Finalize Design]:::humanStep
    F -- No --> H[Retrain ML Models & Refine Design]:::mlStep

    H --> D
    G --> I[Validation & Benchmarking]:::humanStep
    I --> J[Ethics & Sustainability Assessment]:::humanStep
    J --> K[Interdisciplinary Collaboration]:::humanStep
    K --> L[Document Challenges & Limitations]:::humanStep
    L --> M[Future Work & Improvements]:::humanStep
    M --> N[Project End / Next Iteration]:::defaultStep

    %% Iterative feedback loops with curved arrows
    C -- Iterative feedback --> E
    E -- Simulation results --> C
    D -- Design iterations --> E
    E -- Performance informs --> D

    %% Loop arrows styling
    linkStyle 12 stroke:#0b3d91,stroke-width:2px,stroke-dasharray:5,5
    linkStyle 13 stroke:#9b2226,stroke-width:2px,stroke-dasharray:5,5
    linkStyle 14 stroke:#0b3d91,stroke-width:2px,stroke-dasharray:5,5

    %% Legend definition below main chart
    subgraph LEGEND [Legend]
        direction TB
        ML["■ ML-driven steps"]:::mlStep
        SIM["■ Simulation-driven steps"]:::simStep
        HUMAN["■ Human-in-the-loop steps"]:::humanStep
        DEFAULT["■ Other / Start & End"]:::defaultStep
    end


# References

- Andersen, R.K., et al. (2014). *Uncertainty and variability in building energy performance simulation*. Energy and Buildings, 81, 141–151. https://doi.org/10.1016/j.enbuild.2014.05.057  
- Ascione, F., et al. (2017). Machine learning models for predicting building energy consumption: A review. *Renewable and Sustainable Energy Reviews*, 75, 1286-1299. https://doi.org/10.1016/j.rser.2016.11.214  
- Bendsøe, M.P. & Sigmund, O. (2003). *Topology Optimization: Theory, Methods, and Applications*. Springer.  
- Breiman, L. (2001). Random Forests. *Machine Learning*, 45(1), 5-32. https://doi.org/10.1023/A:1010933404324  
- Costa, A. & Shen, Z. (2015). Energy prediction accuracy and gaps in building simulation. *Building Simulation*, 8(4), 423–432. https://doi.org/10.1007/s12273-015-0234-0  
- Crawley, D.B., et al. (2008). EnergyPlus: Creating a new-generation building energy simulation program. *Energy and Buildings*, 40(1), 49–61. https://doi.org/10.1016/j.enbuild.2007.01.019  
- Eastman, C., et al. (2018). *BIM Handbook: A Guide to Building Information Modeling for Owners, Designers, Engineers, Contractors, and Facility Managers* (3rd ed.). Wiley.  
- EnergyPlus Weather Data (2024). *EnergyPlus Weather Files*. U.S. Department of Energy. Retrieved from https://energyplus.net/weather  
- eTool (2023). *Life Cycle Assessment Software for Buildings*. Retrieved from https://etoolglobal.com/  
- Fortin, F.-A., et al. (2012). DEAP: Evolutionary Algorithms Made Easy. *Journal of Machine Learning Research*, 13, 2171–2175.  
- Goodfellow, I., Bengio, Y., & Courville, A. (2016). *Deep Learning*. MIT Press.  
- Jolliffe, I.T. & Cadima, J. (2016). Principal component analysis: a review and recent developments. *Philosophical Transactions of the Royal Society A*, 374(2065), 20150202. https://doi.org/10.1098/rsta.2015.0202  
- Kohavi, R. (1995). A Study of Cross-Validation and Bootstrap for Accuracy Estimation and Model Selection. *International Joint Conference on Artificial Intelligence (IJCAI)*, 14(2), 1137–1145.  
- Kotsiantis, S.B., Zaharakis, I., & Pintelas, P. (2006). Machine learning: a review of classification and combining techniques. *Artificial Intelligence Review*, 26(3), 159–190. https://doi.org/10.1007/s10462-007-9052-3  
- Li, Z., et al. (2019). Feature extraction in building energy prediction: A review. *Sustainable Cities and Society*, 52, 101847. https://doi.org/10.1016/j.scs.2019.101847  
- Lundberg, S.M. & Lee, S.-I. (2017). A Unified Approach to Interpreting Model Predictions. *Advances in
