## 📓 Jupyter Notebooks

This folder contains all the experimental and development notebooks used for data exploration, machine learning model development, and generative design testing. These notebooks reflect the iterative and research-driven nature of the project.

---

### 🧭 Notebook Overview by Learning Phase

To align with the [Learning Roadmap](../learning_roadmap/README.md), notebooks are organized by the key phases of skill acquisition and project development.

#### 🏗️ Phase 1: Foundations (Python, Data Parsing, Energy File Formats)

* **[01_data_visualisation.ipynb](01_data_visualisation.ipynb)**
    * **Purpose:** Initial data exploration and visualization of raw inputs.
    * **Contents:** Loading and inspecting raw datasets (e.g., geometry, weather data). Plotting distributions of input parameters.
    * **Goal:** Gain insight into data characteristics and initial correlations relevant for energy performance.

#### 🧠 Phase 2: Machine Learning for Energy Prediction

* **[02_regression_energy.ipynb](02_regression_energy.ipynb)**
    * **Purpose:** Develop and evaluate machine learning surrogate models for energy performance prediction.
    * **Contents:** Preprocessing of input data. Training various regression models (e.g., Linear Regression, Random Forest, Gradient Boosting). Evaluating model accuracy (e.g., MAE, RMSE, R²).
    * **Goal:** Create a robust and fast predictive model that can estimate Energy Use Intensity (EUI) based on early-stage design features, to serve as a fitness function for generative design.

#### 🧩 Phase 3: ML-Integrated Generative Design

* **[03_generative_ga_layouts.ipynb](03_generative_ga_layouts.ipynb)**
    * **Purpose:** Implement generative design techniques (e.g., Genetic Algorithms) to explore and optimize architectural layouts.
    * **Contents:** Encoding room and layout constraints. Defining objective functions (e.g., using the trained energy prediction model from Phase 2). Iteratively generating, mutating, and evaluating floorplans.
    * **Goal:** Explore diverse design options that improve energy efficiency automatically while adhering to spatial constraints.

*(Add more notebooks here as you develop, categorized under the relevant phase)*

---

### 📝 Notes & Workflow

* These notebooks are primarily **exploratory and developmental**. They are used for rapid prototyping and testing of ideas.
* Once methodologies or components are stable and proven in these notebooks, the robust, reusable code will be **refactored into Python scripts** in the `src/` directory.
* Results presented in these notebooks are often initial findings. For final validation and deployment in full simulation workflows, please refer to the `src/` and `tools/` directories.
* The progress documented in these notebooks directly contributes to the milestones outlined in the [Learning Roadmap](../learning_roadmap/README.md).

---

### ⚙️ How to Use & Reproduce

* **Environment Setup:** To run these notebooks, please ensure you have the necessary dependencies installed. Refer to the `environment.yml` file in the root directory of this repository for a complete list of required packages.
* **Execution:** Notebooks are typically designed to be run sequentially within their respective categories.

---

### 🔍 Next Steps for Notebook Development

* Integrate Ladybug Tools data directly into notebooks for weather-driven simulations and more robust data generation.
* Explore linking predictive models and generative workflows to geometry engines (e.g., Grasshopper/Revit) via their APIs for real-time feedback.
* Begin testing generation workflows with real-world site parameters and climate adaptation scenarios.
* Develop dedicated notebooks for Reinforcement Learning (RL) agent training and Explainable AI (XAI) technique demonstration.

---

### 📚 Related Files & Directories

* [`data/`](../data/README.md): Contains input and processed datasets used by these notebooks.
* [`src/`](../src/README.md): Houses reusable Python scripts and modules refactored from notebooks.
* [`docs/`](../docs/README.md): Provides broader project documentation, including research questions and methodology.
* [`results/`](../results/README.md): (If you create one) Where key outputs, figures, or final processed data from notebooks are stored.
