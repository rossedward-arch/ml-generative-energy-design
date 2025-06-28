# Methodology

## 🔍 Abstract

This methodology proposes a machine learning–assisted generative design framework tailored for high-performance architecture. It integrates Passivhaus and Net Zero principles into early design stages via simulation-informed optimization, explainable AI, and iterative feedback loops. The approach prioritizes transparency, scalability, and energy equity by combining human-in-the-loop design, digital twins, and real-time data calibration.

## 📑 Table of Contents

1. [Research Approach](#1-research-approach)  
2. [Data Sources & Processing](#2-data-sources--processing)  
3. [Machine Learning Methods](#3-machine-learning-methods)  
4. [Generative Design Workflow](#4-generative-design-workflow)  
5. [Energy Simulation Integration](#5-energy-simulation-integration)  
6. [Software Tools & Dissemination](#6-software-tools-user-experience--dissemination)  
7. [Challenges & Assumptions](#7-challenges--assumptions)  
8. [Future Work](#8-future-work)  
9. [Ethical & Sustainability Considerations](#9-ethical--sustainability-considerations)  
10. [Interdisciplinary Collaboration](#10-interdisciplinary-collaboration)  
11. [Documentation & Reporting](#11-documentation--reporting)  
12. [References](#references)

## 1. Research Approach

This methodology is specifically tailored for the early-stage design and optimization of new high-performance building projects.It extends prior ML–generative design frameworks by embedding Passivhaus and Net Zero principles at the conceptual stage, with a focus on new builds where design flexibility, data quality, and regulatory alignment are maximized. The approach prioritizes energy performance and occupant comfort through an iterative, data-driven feedback loop, leveraging the standardized data and construction practices typical of new construction.

Unlike previous approaches, this integration emphasizes automation and predictive analytics at the early-stage decision-making level, targeting new builds that seek Passivhaus certification and Net Zero energy performance. By focusing on new construction, the methodology ensures that all predictive modeling, simulation, and optimization steps are based on current best practices, modern materials, and up-to-date regulatory requirements.

This research addresses a critical gap by unifying early-stage generative design with continuous ML-predicted energy feedback for new buildings, enabling compliance with Passivhaus and Net Zero standards from the outset—an integration not extensively realized in current architectural design pipelines for new construction.

This methodology incorporates **explainable AI (XAI)**, **multi-criteria decision analysis (MCDA)**, and **equity auditing** to ensure transparency, stakeholder alignment, and social responsibility across new build typologies. The pipeline is cloud-ready, scalable, and designed for continuous improvement via **human-in-the-loop active learning** and **real-time IoT data integration** from new build pilot projects.

- **Predictive Modeling:** Machine learning techniques predict building energy use and occupant comfort based on early design parameters such as geometry, orientation, and material specifications, all derived from BIM models typical of new construction (Ascione et al., 2017; Goodfellow et al., 2016). 
- **Generative Optimization:** Genetic algorithms iteratively explore the design space for new builds, optimizing layouts, envelope performance, and renewable integration for energy efficiency and comfort, guided by simulation feedback and ML predictions (Mitchell, 1998; Bendsøe & Sigmund, 2003).  
- The integration of Passivhaus principles (airtightness, insulation, ventilation) and Net Zero targets is specifically adapted to new build scenarios, providing a robust framework that ensures designs meet stringent energy and sustainability goals from the outset (Passivhaus Trust, 2024; UK Government, 2021).

### Industry Integration & Scalability
- **Pilot Projects:** The methodology includes a framework for conducting pilot implementations with architectural firms, focusing on collecting real-world feedback and measuring practical performance gains.
- **Scalability Assessment:** Protocols are established to assess how the methodology scales from individual building designs to neighborhood or district-level applications, addressing computational and data management challenges.
- **Economic Impact Evaluation:** Economic assessment frameworks are integrated to quantify the cost-benefit relationships of using this methodology compared to traditional design approaches, demonstrating its value proposition to the industry.

---

## 2. Data Sources & Processing

The project utilizes standardized, high-quality datasets specific to new-build projects to support machine learning and energy simulation tasks:

- **Building Geometry and Design Parameters:** BIM exports (e.g., Revit, IFC) from new construction projects, providing accurate spatial layouts, zoning, and material specifications as defined in current design documentation (Eastman et al., 2018; Revit, 2023).
Legacy or retrofit-specific data is excluded to ensure consistency and relevance to new builds.  
- **Weather Data:** Typical meteorological year files (EPW format) for the proposed site of each new build, supporting climate-responsive design (EnergyPlus Weather Data, 2024).  
- **Energy Simulation Outputs:** EnergyPlus or OpenStudio results capturing Energy Use Intensity (EUI), thermal comfort, and HVAC loads, based on idealized new-build assumptions (Crawley et al., 2008).  
- **Performance Benchmarks:** Passivhaus and Net Zero targets for new construction are used as validation criteria and for model calibration (Passivhaus Trust, 2024; UK Government, 2021).  
- **IoT Sensor Streams:** Where available, real-time data from recently completed new builds is used for digital twin validation and model recalibration. If not available, simulated post-occupancy data or literature benchmarks are used for validation.
- **Equity and Bias Auditing:** Datasets are regularly audited for representation and fairness across new build typologies (e.g., residential, educational, commercial) and urban/rural contexts. Audits focus on ensuring the framework is inclusive for diverse new construction scenarios.

**Data Pipeline Enhancements:**
- **Active Learning:** The model uses uncertainty sampling to request the most informative new-build design cases for faster learning.
- **Transfer Learning:** Incorporates external new-build datasets (e.g., open data from UK or EU new construction) to improve generalization.

> The majority of data is tabular or spatial-temporal, with formats including CSV, JSON, and IDF.  
> Datasets are organized into reproducible data pipelines ensuring consistency  and scalability for new-build simulation and model training workflows.

> Geometric data from BIM platforms (e.g., Revit) is translated into simulation-ready inputs via IFC parsers or custom Dynamo scripts, extracting relevant attributes (surface areas, zoning, materials) for new-build-specific EnergyPlus-compatible IDF files.

> To address variability in design and climate conditions, uncertainty in inputs—such as occupancy schedules and weather profiles—is handled using stochastic sampling or Monte Carlo simulation, supporting robust predictions for a range of new-build scenarios.

### 2.1 Data Preprocessing and Feature Engineering Enhancements
- **Bias Detection & Mitigation:** Protocols focus on identifying and addressing underperformance for specific new build typologies or site contexts in the input data and model training..
- **Equity Auditing:** Regular reviews ensure fair and inclusive outcomes for all relevant new-build categories by assessing dataset representativeness.
- **Ethical Oversight:** Compliance with data privacy, consent, and responsible AI guidelines is maintained throughout data collection, processing, and model deployment for new construction projects.
---

## 🔄 Data Flow Diagram

```mermaid
flowchart TD
    A["Building Geometry\n(BIM / Revit / IFC)"] --> B["Feature Extraction"]
    E["Climate & Weather Data\n(EPW files)"] --> B
    X["IoT Sensor Streams"] --> K["Digital Twin Feedback"]
    Y["Equity Auditing Data"] --> L["Equity Audit Reports"]
    B --> C["Simulation Configuration\n(IDF / OpenStudio)"]
    F["Performance Benchmarks\n(Passivhaus / Net Zero)"] --> C
    C --> D["Energy Simulation\n(EnergyPlus)"]
    D --> G["Simulation Results\n(CSV / SQLite)"]
    B --> H["ML-ready Features\n(CSV / Parquet)"]
    G --> I["Model Training\n(ML Algorithms)"]
    H --> I
    I --> J["Energy Performance Predictions\n(EUI, Comfort, Loads)"]
    K --> I
    L --> I

    style A fill:#e6f7ff,stroke:#3399cc,color:#000000
    style E fill:#e6f7ff,stroke:#3399cc,color:#000000
    style F fill:#e6f7ff,stroke:#3399cc,color:#000000
    style X fill:#e0f7fa,stroke:#00acc1,color:#000000
    style Y fill:#fff2cc,stroke:#e69138,color:#000000
    style B fill:#fff2cc,stroke:#e69138,color:#000000
    style C fill:#fff2cc,stroke:#e69138,color:#000000
    style D fill:#fde9d9,stroke:#d6604d,color:#000000
    style G fill:#f4cccc,stroke:#cc0000,color:#000000
    style H fill:#f4cccc,stroke:#cc0000,color:#000000
    style I fill:#d9ead3,stroke:#38761d,color:#000000
    style J fill:#d9ead3,stroke:#38761d,color:#000000
    style K fill:#f1f8e9,stroke:#558b2f,color:#000000
    style L fill:#f1f8e9,stroke:#558b2f,color:#000000
```
> ⚠️ Note: If diagrams do not render on GitHub, use [Mermaid Live Editor](https://mermaid.live/edit) or export as SVG.

### 2.2 Feature Engineering Techniques.

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
| **Input**          | Building Geometry        | JSON, DXF, IFC   | Parametric models or predefined layouts; includes floor area, WWR, zoning      |
|                    | Climate / Weather Data   | EPW              | Hourly weather profiles: temperature, radiation, humidity                      |
|                    | Construction Benchmarks  | CSV, JSON        | U-values, infiltration rates, HVAC presets from Passivhaus datasets            |
|                    | IoT Sensor Streams       | JSON, CSV        | Real-time data from built projects for digital twin validation                 |
|                    | Equity Auditing Data     | CSV, JSON        | Demographic, typology, and usage data for bias and fairness assessment         |
| **Transformation** | Feature Extraction       | Tabular          | Derives ratios, materials, orientations, envelope metrics                      |
|                    | Data Cleaning & Encoding | Tabular          | One-hot encoding for categories; normalization for numeric data                |
|                    | Simulation Configuration | IDF (EnergyPlus) | Translated inputs used for energy and comfort simulations                      |
| **Output**         | Simulation Results       | CSV, SQLite      | Outputs include EUI, daylight autonomy, overheating hours                      |
|                    | ML-ready Feature Sets    | CSV, Parquet     | Cleaned and structured datasets for training and evaluation                    |
|                    | Digital Twin Feedback    | JSON, CSV        | IoT-driven post-occupancy data for model recalibration and validation          |
|                    | Equity Audit Reports     | PDF, CSV         | Reports on model fairness and bias detection                                   |

---

## 3. Machine Learning Methods

### Overview:
The machine learning component is specifically designed for new-build projects, leveraging the standardized data quality and design flexibility typical of modern construction. All models are trained and validated exclusively on new-build datasets, ensuring predictions are robust and relevant to current industry practices and regulatory targets.

### Model Selection and Justification

- **Models Used:**  
  - Linear Regression and Random Forest for initial regression tasks, offering interpretability and insight into key design drivers (Breiman, 2001).  
  - Neural Networks (TensorFlow/Keras) for capturing complex, multivariate relationships in new-build energy and comfort data (Goodfellow et al., 2016).
  - Ensemble Stacking to further enhance prediction accuracy within the new-build domain.

- **Model Selection Justification:**  
  - The homogeneity and completeness of new-build BIM and simulation data allow for more reliable model training and validation. 
  - Feature importance analysis is particularly actionable for new builds, where design parameters can be flexibly adjusted. 

- **Learning Approaches**  
  - **Supervised Learning:**
    - Primary approach for predicting energy use, comfort, and Net Zero compliance from early-stage new-build design parameters.

  - **Active Learning:**
    - The model identifies the most informative new-build design cases for targeted simulation and data enrichment, accelerating learning and reducing computational load.

  - **Transfer Learning:**
    - Where appropriate, transfer learning incorporates external new-build datasets (e.g., UK/EU open data) to improve model generalization within the new-build context.

- **Training:**  
  - Data split into training, validation, and test sets are preformed on new-cases only.  
  - Hyperparameter tuning and cross-validation optimize model performance (Kohavi, 1995).
  - **Automated Hyperparameter Optimization:** Bayesian optimization (Optuna/Hyperopt) for all ML and GA parameters, with a focus on optimizing for new-build performance metrics.
  - EnergyPlus or OpenStudio simulation-only results for new builds serve as the primary baseline, quantifying the added value of ML predictions.

- **Evaluation Metrics:**  
  - Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), and R² score, evaluated specifically for new-build performance targets (Willmott & Matsuura, 2005)
  - Additional evaluation against Passivhaus and Net Zero new-build benchmarks.

- **Interpretability and Explainability:**  
  - XAI Tools 
   - SHAP, LIME, and custom dashboards provide transparent rationales for all new-build predictions, supporting design decision-making.
   - Feature importance is reported for new-build design parameters, such as envelope U-values, window-to-wall ratio, and renewable system sizing.

- **Uncertainty Quantification:**  
  - Bayesian methods and Monte Carlo dropout provide predictive confidence intervals, supporting robust early-stage decisions for new builds.

- **Ethics & Bias & Equity:**  
  - **Fairness Auditing:**
    - Regular audits focus on detecting and mitigating bias across new-build typologies (e.g., residential, educational, commercial) and site contexts (urban/rural).
  - **Mitigation:**
    - Any detected bias is addressed through targeted data augmentation or model adjustment, ensuring inclusive new-build design recommendations.

- **Continuous Improvment** 
  - **Model Upating:**
    - The system is designed for continuous improvement, with new data from completed new builds (including post-occupancy or digital twin data where available) incorporated to refine predictions and maintain relevance as industry standards evolv


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

    style A fill:#e6f7ff,stroke:#3399cc,color:#000000
    style B fill:#fff2cc,stroke:#e69138,color:#000000
    style C fill:#fde9d9,stroke:#d6604d,color:#000000
    style D fill:#f4cccc,stroke:#cc0000,color:#000000
    style E fill:#d9ead3,stroke:#38761d,color:#000000
    style F fill:#cfe2f3,stroke:#3d85c6,color:#000000
    style G fill:#c9daf8,stroke:#6d9eeb,color:#000000
```

## 4. Generative Design Workflow

This section outlines the generative design process, specifically adapted for new-build projects. The workflow leverages the design flexibility and standardized data available in new construction, enabling robust optimization and automation of high-performance building layouts.

- **Algorithm:** 
  - Genetic Algorithms (GAs) implemented via the DEAP library (Fortin et al., 2012).
  - Rationale: GAs are well-suited for exploring the large, multi-dimensional design space typical of new builds, where form, orientation, and envelope specifications can be freely optimized.

- **Design Encoding:** 
  - Parameters represent building layouts, including room sizes, orientations, spatial adjacencies, and envelope specifications (Mitchell, 1998).  
  - Layouts are parameterized using:
    - **Bounding boxes** for spaces
    - **Adjacency matrices** to enforce connectivity rules
    - **Spline-based controls** for flexible envelope geometry adaptation
  -Rationale: New-build projects allow full control over these parameters, enabling more effective optimization compared to retrofits.

- **Optimization:**  
  - Multi-objective GA balances trade-offs between energy use, thermal comfort, and compliance with Passivhaus and Net Zero standards for new construction. 
  - Rationale: Focusing on new builds ensures that all design variables are within the architect’s control, maximizing the potential for energy and comfort optimization.

- **Simulation-ML Feedback:**
  - Each candidate design is evaluated using EnergyPlus or OpenStudio simulations, with results used to train and validate ML models. 
  - ML predictions guide the GA’s selection and mutation of designs, accelerating the search for optimal solutions..  
  - Rationale: New-build data allows for consistent, high-quality simulation and ML feedback, improving the reliability of design recommendations.

- **Iterative Refinement**
  - The workflow iteratively refines designs based on simulation and ML feedback, with each cycle improving energy performance and comfort.
  - Rationale: The iterative process is more effective in new builds, where design changes can be implemented without legacy constraints.

- **Senario Testing**
  - Designs are tested against multiple future climate, regulatory, and market scenarios to ensure robustness and adaptability.
  - Rationale: New-build projects must be resilient to future changes, making scenario testing essentia.

- **Outcome**
  - The workflow produces a set of Pareto-optimal new-build designs that balance energy efficiency, comfort, and regulatory compliance.
  - Rationale: This ensures that the methodology supports architects in making informed, evidence-based decisions for high-performance new construction.

---

### 🧬 Generative Design and Simulation Loop

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

    style A fill:#e0f7fa,stroke:#00acc1,color:#000000
    style B fill:#f1f8e9,stroke:#558b2f,color:#000000
    style C fill:#fff9c4,stroke:#fbc02d,color:#000000
    style D fill:#f0f4c3,stroke:#c0ca33,color:#000000
    style E fill:#e1bee7,stroke:#8e24aa,color:#000000
    style F fill:#ffccbc,stroke:#e64a19,color:#000000
    style G fill:#ffe082,stroke:#ff6f00,color:#000000
    style H fill:#c8e6c9,stroke:#43a047,color:#000000
```

## 5. Energy Simulation Integration

This section details how energy simulation is integrated into the design and optimization process, with all workflows and assumptions specifically adapted for new-build projects.

- **Simulation Engine Selection:** 
  - EnergyPlus (with OpenStudio as an interface) is used as the primary simulation engine, due to its industry-standard status and robust support for new-build performance modeling.  
    *(Rationale: EnergyPlus provides detailed, validated simulation of building physics and is widely used for Passivhaus and Net Zero compliance in new construction.)*
- **Model Preparation and Input Generation:**
  - Building geometry, zoning, and material specifications are exported directly from BIM models (e.g., Revit, IFC) for each new-build project. Custom scripts translate BIM data into EnergyPlus-compatible IDF files.  
   *(Rationale: New builds provide standardized, high-quality BIM data, reducing errors and manual input during simulation setup.)*
- **Simulation Assumptions:** 
- All simulations assume modern construction quality, up-to-date insulation, airtightness, and HVAC systems as specified in the design. Occupancy schedules and internal loads are based on current best-practice guidelines for new construction.  
  *(Rationale: This ensures simulation results are realistic and directly relevant to the performance of new builds.)*
- **Simulation Outputs:**   
  - Simulations generate Energy Use Intensity (EUI), thermal comfort hours, overheating risk, and renewable energy generation potential. Results are benchmarked against Passivhaus and Net Zero targets for new construction.
  *(Rationale: Focusing on these metrics aligns the workflow with regulatory and industry requirements for high-performance new builds.)*
- **Integration with Generative Design and ML:**    
  - Simulation results are used to train, validate, and calibrate ML models, which in turn guide generative design optimization. High-fidelity simulations are retained for a representative sample of new-build designs to ensure ML predictions remain accurate and reliable.  
  *(Rationale: This approach balances computational efficiency with predictive accuracy, leveraging the consistency of new-build data.)*
- **Scenario and Sensitivity Analysis:** 
  - Designs are simulated under multiple climate scenarios and regulatory assumptions to test robustness. Sensitivity analysis identifies which new-build design parameters have the greatest impact on performance.  
  *(Rationale: New builds must be resilient to future uncertainties; scenario testing ensures robust, future-proof designs.)*

- **Validation and Continuous Improvement:**  
  - Where available, simulation results are validated against post-occupancy or digital twin data from completed new builds. Discrepancies are used to recalibrate simulation assumptions and update ML models.  
  *(Rationale: Closing the loop with real-world data improves long-term reliability and trust in the methodology.)*

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

    style A fill:#f0f8ff,stroke:#4682b4,color:#000000
    style B fill:#e6f7ff,stroke:#66afe9,color:#000000
    style C fill:#fde9d9,stroke:#d6604d,color:#000000
    style D fill:#fbe9e7,stroke:#ef6c00,color:#000000
    style E fill:#fff8dc,stroke:#e6ac00,color:#000000
    style F fill:#e1f5fe,stroke:#0288d1,color:#000000
    style G fill:#dcedc8,stroke:#7cb342,color:#000000
    style H fill:#ffe0b2,stroke:#f57c00,color:#000000
    style I fill:#f3e5f5,stroke:#9c27b0,color:#000000
    style J fill:#e8f5e9,stroke:#43a047,color:#000000
```

## 6. Software Tools, User Experience & Dissemination

- **Core Software Stack:**  
  - **BIM & Geometry:** Autodesk Revit, IFC, Dynamo for parametric modeling and data extraction.
  - **Simulation:** EnergyPlus, OpenStudio for energy and comfort simulation.
  - **ML & Optimization:** Python (scikit-learn, TensorFlow/Keras, DEAP, Optuna/Hyperopt).
  - **Data Processing:** Pandas, NumPy, custom scripts for feature engineering and data cleaning.
  - **Visualization:** Power BI, Plotly, custom dashboards for interpretability and stakeholder engagement.

- **User Experience:**  
  - Modular, scriptable pipeline for integration into existing architectural workflows.
  - GUI prototypes or Jupyter notebooks for interactive exploration and visualization.
  - Documentation and example projects for reproducibility.

- **Dissemination:**  
  - Source code and data pipelines shared via GitHub (where licensing permits).
  - Results disseminated through academic publications, conference presentations, and workshops with industry partners.
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
| **User Constraints**                    | Aesthetic, cost, and functional decisions may be missed by automated workflows  | Include manual review stages; designer-in-the-loop (manual overrides and feedback integration) interventions   | Gerber et al., 2012                                           |
| **Domain Transferability**              | Model may underperform on unseen typologies or climates                         | Out-of-sample validation; ensemble models for broader generality   | Zhang et al., 2020                                            |

> Bias and Overfitting Risk: Since early-stage data may be sparse or imbalanced, overfitting remains a critical risk—especially with high-capacity models like neural networks. Techniques such as regularization, dropout, and k-fold cross-validation are employed to mitigate this.

> Realistic User Constraints: Design decisions in practice often depend on subjective criteria such as aesthetics, cost, or policy—which are difficult to encode into purely performance-based models. To account for this, the system supports **manual overrides** and **designer-in-the-loop (manual overrides and feedback integration) feedback loops**.

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

    style A1 fill:#f9f,stroke:#333,color:#000000
    style A2 fill:#f9f,stroke:#333,color:#000000
    style A3 fill:#f9f,stroke:#333,color:#000000
    style A4 fill:#f9f,stroke:#333,color:#000000
    style A5 fill:#f9f,stroke:#333,color:#000000
    style A6 fill:#f9f,stroke:#333,color:#000000
    style A7 fill:#f9f,stroke:#333,color:#000000
    style A8 fill:#f9f,stroke:#333,color:#000000
    style B1 fill:#d9fdd3,stroke:#333,color:#000000
    style B2 fill:#d9fdd3,stroke:#333,color:#000000
    style B3 fill:#d9fdd3,stroke:#333,color:#000000
    style B4 fill:#d9fdd3,stroke:#333,color:#000000
    style B5 fill:#d9fdd3,stroke:#333,color:#000000
    style B6 fill:#d9fdd3,stroke:#333,color:#000000
    style B7 fill:#d9fdd3,stroke:#333,color:#000000
    style B8 fill:#d9fdd3,stroke:#333,color:#000000
```

## 8. Future Work

- **Scalability:**  
  - Expansion to district/neighborhood-scale modeling and optimization.
  - Integration with urban energy models and city-level digital twins.

- **Retrofitting & Mixed-Use:**  
  - Adapting the framework for retrofit projects and mixed-use developments.

- **Advanced ML & Automation:**  
  - Incorporation of reinforcement learning, unsupervised clustering, and automated design space exploration.

- **Longitudinal Validation:**  
  - Ongoing collection of post-occupancy and IoT data for continuous model improvement and validation.
---

## 9. Ethical & Sustainability Considerations

- **Equity Auditing:**  
  - Regular audits to ensure fair and inclusive recommendations across new-build typologies and demographics.

- **Data Privacy:**  
  - All data collection and processing comply with GDPR and university ethical guidelines.

- **Sustainability:**  
  - The methodology is designed to maximize environmental and social benefit, supporting Net Zero and Passivhaus targets.


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

## 11.1 Methodology Workflow Diagram

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

    %% Vertical legend using separate flow
    subgraph LegendColumn[Legend]
        direction TB
        L1["■ ML-driven steps"]:::mlStep
        L2["■ Simulation-driven steps"]:::simStep
        L3["■ Human-in-the-loop steps"]:::humanStep
        L4["■ Other / Start & End"]:::defaultStep
        L1 --> L2 --> L3 --> L4
    end
```

## License

This methodology is shared under the Creative Commons Attribution 4.0 International (CC BY 4.0) License. You may share and adapt the material with attribution.

## How to Cite

> Author Edward, R. (2025). *Methodology: Machine Learning–Assisted Generative Design for Energy-Efficient Architecture*. GitHub. https://[github.com/yourusername/yourrep](https://github.com/rossedward-arch/ml-generative-energy-design)

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
