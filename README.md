# ML for Sustainable Architecture: A Research Portfolio

## ⚙️ Integrated ML & Generative Design for Climate-Adapted Energy-Efficient Buildings

-A research-driven project integrating reinforcement learning, explainable AI, generative design, and energy performance simulation to support early-stage architectural decision-making for climate-adapted, Passivhaus, and net-zero buildings.--

---

## 🚧 Project Status
This project is under active development as part of a personal research portfolio, showcasing my continuous learning and practical application of Machine Learning for a potential PhD application at institutions like Edinburgh University..


## 🎯 Goals
- To automate early-stage building layout generation using generative design and reinforcement learning optimization
- To integrate site conditions (EPW weather, solar orientation, etc.) and climate adaptation data.
- To optimise designs based on energy use intensity (EUI), thermal comfort, and resilience metrics.
- To evelop explainable AI models to provide transparent, interpretable energy performance predictions.
- To provide a decision-support tool for architects and designers with feedback-driven iterative design.

---

## 🛠️ Technologies & Tools
- Python (Pandas, Scikit-learn, TensorFlow, stable-baselines3 for reinforcement learning, SHAP/LIME for explainability)
- Grasshopper + Ladybug Tools
- Revit (geometry extraction + BIM data)
- Streamlit (interactive design interface)
- EnergyPlus / OpenStudio (performance simulation)
- Git for version control

---

## 🔬 Research Themes
This work is informed by research in:
- Reinforcement learning for adaptive generative design optimization
- Explainable AI techniques for model transparency and decision support
- Generative design for architecture and layout planning
- Machine learning models for energy prediction
- Early-stage performance-based design
- Passivhaus and zero-energy building standards

📖 See `docs/literature_review.md` for citations and background readings.

---

## 📚 Learning Roadmap & Skills
This project is also part of a structured self-learning journey to prepare for PhD-level research. Key learning milestones:

| Stage | Topic | Tools / Books | Outcome |
|-------|----------------------------|--------------------------|---------|
| 1     | Python Fundamentals        | Python Fundamentals    | Basic scripting and data types |
| 2     | Data Analysis              | *Python for Data Analysis* | Manipulate EPW, CSV data |
| 3     | Data Visualisation         | Matplotlib / Seaborn     | Visualise temp, loads, EUI |
| 4     | Machine Learning (Scikit)  | *Hands-On ML* by Géron   | Train energy prediction models |
| 5     | Generative Design          | DEAP, Grasshopper        | Optimise layouts with GA |
| 6     | Simulation Integration     | Ladybug, OpenStudio      | Link ML to real energy engines |
| 7     | UI / App Interface         | Streamlit / Dash         | Design explorer prototype |

📁 See project notebooks and `docs/dev_log.md` for progress.

---

## 📁 Repo Structure

```text
ml-generative-energy-design/
│
├── data/                        ← Raw & processed datasets (CSV, JSON, EPW)
├── notebooks/                  ← Jupyter Notebooks for ML and analysis
├── src/                        ← Core Python modules
├── results/                    ← Model outputs, charts, and metrics
├── tools/                      ← Scripts for Grasshopper/Ladybug/Revit
├── docs/                       ← Research logs, literature review, dev notes
├── learning_roadmap/           ← Books, projects, tutorials, learning logs
├── app/                        ← Optional UI with Streamlit or Dash
│
├── .gitignore
├── environment.yml             ← Conda environment
├── LICENSE
├── README.md
├── CITATION.cff

```
---
## 📚 References
See `docs/literature_review.md` for citations and background readings.


## 👤 Author
Ross Edward — MSc in Architectural Technology and Energy Performance, Edinburgh Napier University  

## 🧪 Citation
Please cite this repo using the `CITATION.cff` file if used in publications.

