# 📓 Jupyter Notebooks

This folder contains all the experimental and development notebooks used for data exploration, machine learning model development, and generative design testing. These notebooks reflect the iterative and research-driven nature of the project.

---

## 🧭 Notebook Overview

### `01_data_visualisation.ipynb`
- **Purpose:** Initial data exploration and visualisation.
- **Contents:**
  - Loading and inspecting raw datasets (e.g. geometry, weather data)
  - Plotting distribution of input parameters
  - Exploring correlations between design parameters and energy use
- **Goal:** Gain insight into which features matter most for energy performance.

---

### `02_regression_energy.ipynb`
- **Purpose:** Develop machine learning models to predict energy performance.
- **Contents:**
  - Preprocessing of input data
  - Training regression models (e.g. Linear Regression, Random Forest, etc.)
  - Evaluating accuracy (e.g. MAE, R²)
- **Goal:** Create a predictive model that can estimate EUI based on early-stage design features.

---

### `03_generative_ga_layouts.ipynb`
- **Purpose:** Use generative design (e.g. Genetic Algorithms) to optimise layouts.
- **Contents:**
  - Encoding room and layout constraints
  - Iteratively generating and mutating floorplans
  - Evaluating fitness using energy predictions
- **Goal:** Explore design options that improve energy efficiency automatically.

---

## 📝 Notes

- Notebooks are exploratory in nature — some cells may contain placeholder content or draft code.
- Results should be validated with full simulation workflows later in the `src/` and `tools/` directories.

---

## 🔍 Next Steps

- Integrate Ladybug data for weather-driven simulations.
- Link predictive models to geometry engines (e.g. Grasshopper/Revit) via APIs.
- Begin testing generation workflows with real site parameters.

---

## 📚 Related Files

- `data/`: Input and processed datasets
- `src/`: Python scripts that support the notebooks
- `docs/literature_review.md`: Academic foundations and references

