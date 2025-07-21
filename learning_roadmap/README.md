# PhD Readiness: Integrated ML, Generative Design & Energy Simulation

This repository is a structured learning roadmap to prepare for a PhD focused on **Integrated Reinforcement Learning and Explainable AI for Climate-Adapted Generative Design of Passivhaus and Net-Zero Buildings**. It combines Python, machine learning, parametric design, and building performance simulation using tools like EnergyPlus, OpenStudio, and Grasshopper.

---

## 📚 Overview

This roadmap is organized into five progressive phases:

1. **Foundations** – Python, data parsing, and energy file formats.
2. **Machine Learning for Energy Prediction** – Surrogate models for energy analysis.
3. **ML-Integrated Generative Design** – Parametric workflows with ML feedback.
4. **Simulation-ML Feedback Loops** – Automating and retraining simulation workflows.
5. **Portfolio & Research Extensions** – Climate adaptation, XAI, and whole-life carbon modeling.

---

## 🗂️ Repository Structure

```text
learning_roadmap/
│
├── README.md                         # Main learning roadmap index
│
├── 00_overview/
│   ├── README.md                     # Overview of the entire roadmap
│   ├── 01_checklist.md               # Phase-wise checklist
│   └── 02_resources_reading.md       # Key learning resources, books, courses
│   └── tutorial_links.md             # Quick-access online tutorials, documentation, and specific practical tools
│
├── 01_foundations/
│   ├── README.md                              # Homepage for Foundations phase
│   ├── 01_progress_log.md                     # Daily/weekly logs for this phase
│   ├── 02_notes_python_fundamentals.md        # Synthesized notes on Python basics (from 100 Days, Udemy, etc.)
│   └── 03_notes_energy_file_formats.md        # Synthesized notes on energy file formats
│   └── 05_notes_numpy_for_data.md             # Synthesized notes on NumPy 
│   └── 06_notes_pandas_data_manipulation.md   # Synthesized notes on Pandas
│   └── 07_notes_data_visualization.md         # Synthesized notes on Matplotlib/Seaborn
│
├── 02_ml_prediction/
│   ├── README.md                              # Homepage for ML Prediction phase
│   ├── 01_progress_logs.md                    # Progress log for this phase
│   ├── 02_notes_sklearn_basics.md             # Synthesized notes on Scikit-learn
│   ├── 03_notes_pytorch_intro.md              # Synthesized notes on Pytorch
│   └── 04_dataset__preperation.md             # Notes on dataset preparation
│
├── 03_generative_design/
│   ├── README.md                              # Homepage for Generative Design phase
│   ├── 01_progress_log.md                     # Progress log for this phase
│   ├── 02_notes_parametric_design.md          # Synthesized notes on parametric_design
│   └── 03_notes_generative_algorithms.md      # Synthesized notes on generative_algorithms
│
├── 04_feedback_optimization/
│   ├── README.md                              # Homepage for Feedback Optimization phase
│   ├── 01_progress_log.md                     # Progress log for this phase
│   ├── 02_notes_simulation_ml_loops.md        # Synthesized notes on simulation-ML loops
│   └── 03_notes_multi_objective_optimization.md  # Synthesized notes on multi-objective optimization
│
├── 05_portfolio_research_extensions/
│   ├── README.md                              # Summary for this phase
│   ├── 01_progress_log.md                     # Progress log for this phase
│   ├── 02_notes_reinforcement_learning.md     # Synthesized notes on reinforcement learning
│   ├── 03_notes_explainable_ai.md             # Synthesized notes on explainable AI
│   ├── 04_notes_climate_adaptation.md         # Synthesized notes on climate adaptation
│   ├── 06_notes_whole_life_carbon.md          # Synthesized notes on whole-life carbon
│   └── mini_projects/                         # PhD Roadmap-defined projects
│       ├── 01_parse_epw_weather_files
│           ├── main.py
│           ├── notebook_eda.ipynb
│           └── data/
│       ├── 02_visualize_energyplus_csv_outputs/
│           ├── viz_script.py
│           └── data/
│       └── 03_train_ml_models_energy_performance
│           ├── train_model.py
│           └── data/
│
└── 06_archive/
    └── old_versions/
        ├── progress_log_pre_26_06_2025.md (example)
        └── notes_dump.md (example)
```
---

## 🚀 Goal

By completing this roadmap, I will develop an advanced interdisciplinary skill set in:
- Python scripting and data workflows for architectural analysis.
- Machine learning for energy prediction and simulation.
- Parametric and generative design automation.
- Simulation feedback integration and retraining pipelines.
- Climate-adapted, explainable, and Net Zero architectural design research.

---

## 🧭 Usage

1. **Start** with `learning_roadmap/.md` for the full roadmap.
2. Track progress via the `02_progress_log.md` of each phase.
3. Use `projects.md` to manage and submit mini-projects.
4. Explore `reference.md` for supporting materials.
5. Regularly update `02_progress_log.md` with reflections and next steps.

---
## ⚙️ Setup

### 1. Prerequisites:

* **Miniconda/Anaconda** ([recommended for environment management](https://docs.conda.io/en/latest/miniconda.html)).
* **Git** ([for cloning and version control](https://git-scm.com/downloads)).
* **VS Code** ([recommended IDE with Python and Jupyter extensions](https://code.visualstudio.com/download)).
* **EnergyPlus** ([a building energy simulation program](https://energyplus.net/)).
* **OpenStudio** ([a platform for whole building energy modeling](https://openstudio.net/)).
* **Ladybug Tools for Grasshopper** ([for parametric design and environmental analysis within Rhino/Grasshopper](https://www.ladybug.tools/installation.html)).


### 2. Clone the Repository:
```bash
git clone [https://github.com/rossedward-arch/ml-generative-energy-design.git](https://github.com/rossedward-arch/ml-generative-energy-design.git)
cd ml-generative-energy-design/learning_roadmap # Navigate into the learning_roadmap folder
```
### 3. Create Conda Environment (for this learning roadmap):

It's highly recommended to create a dedicated Conda environment to manage the project's dependencies. This ensures that the required Python packages and their versions do not conflict with other projects on your system.
```bash
# Navigate to the root of the cloned repository if you're not already there
# For example, if you are in 'learning_roadmap', you might need to go up one level:
# cd ..

# Create the Conda environment using the provided environment.yml file
conda env create -f environment.yml

# Activate the newly created environment
conda activate phd_roadmap
```
**Note:** If an environment.yml file is not yet available in the repository root, you would typically create it or install packages manually. For this structure, you'd place an `environment.yml` at the `root of ml-generative-energy-design/` (i.e., alongside `learning_roadmap/`). A basic `environment.yml` might look like this:
```yaml
# In a file named 'environment.yml' in the root of your 'ml-generative-energy-design' repository
name: phd_roadmap
channels:
  - conda-forge
  - defaults
dependencies:
  - python=3.9 # Or your preferred Python version
  - numpy
  - pandas
  - matplotlib
  - seaborn
  - scikit-learn
  - pytorch::pytorch # Example for PyTorch; specify version if needed
  - jupyter
  - ipykernel
  - requests
  # Add other libraries as needed for your project phases, e.g.,
  # - honeybee
  # - ladybug
  # - openstudio-sdk # Check specific installation for OpenStudio Python bindings
  # - pip:
  #   - grasshopper-api # Example if a pip package is needed for Grasshopper interaction
  ```

### 4. Install Additional Tools and Libraries:

Some tools and libraries, especially those related to building simulation and parametric design, might require separate installations or specific configurations beyond the Conda environment.

* **EnergyPlus & OpenStudio:** Download and install the latest stable versions from their official websites. Ensure their executables are accessible in your system's PATH if you plan to run them programmatically from Python.
    * [EnergyPlus Official Website](https://energyplus.net/)
    * [OpenStudio Official Website](https://openstudio.net/)
  
* **Ladybug Tools for Grasshopper:** Install these as Rhino/Grasshopper plugins. Refer to the official Ladybug Tools documentation for installation instructions.
    * [Ladybug Tools Documentation](https://www.ladybug.tools/installation.html)

### 5. Verify Installation:

After completing the steps, you can verify your setup.
```bash
# Activate the environment (if not already active)
conda activate phd_roadmap

# Check Python version
python --version

# Check if a few key Python packages are installed (e.g., numpy)
python -c "import numpy; print(numpy.__version__)"

# You might also want to run a simple script from the roadmap, e.g., a test from '01_foundations'
# python 01_foundations/some_test_script.py
```

## 📌 License

This learning roadmap is licensed for personal academic use. You're encouraged to fork and adapt it to your own PhD preparation journey.

---

## 🧠 Acknowledgements

Inspired by work in computational design, environmental simulation, and AI-assisted architecture.

