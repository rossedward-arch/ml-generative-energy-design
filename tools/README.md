## ⚙️ Tools & External Software Integration

This folder houses scripts and definitions specifically designed to integrate with and extend external architectural design and building performance simulation software. These tools are crucial for bridging the gap between parametric modeling environments, simulation engines, and the core Python-based Machine Learning and Generative Design workflows.

---

### 🗂️ Folder Structure & Contents Overview

* **`grasshopper/`**
    * **Purpose:** Contains Grasshopper (.gh) definitions, Python scripts embedded within Grasshopper components, and potentially custom C# components that facilitate parametric modeling, data extraction, or real-time interaction with ML models (via libraries like gRPC or Rhino.Compute).
    * **Examples:** Parametric facade generators, data export components for ML input, geometry visualization tools.

* **`revit/`**
    * **Purpose:** Stores scripts and add-ins for Autodesk Revit. This includes Revit Python Shell scripts, Dynamo graphs, or C#/Python code leveraging the Revit API for geometry extraction, BIM data querying, or model manipulation.
    * **Examples:** Scripts to extract room boundaries, window properties, or material data from Revit models for energy simulation or ML feature generation.

* **`ladybug_openstudio_scripts/`**
    * **Purpose:** Houses specialized scripts or templates for configuring, running, and post-processing simulations using Ladybug Tools and OpenStudio/EnergyPlus, often beyond what is directly handled by the `src/simulation_interface/` Python modules.
    * **Examples:** Custom EnergyPlus IDF modification scripts, OpenStudio measure development, specific simulation setups for advanced climate analysis.

---

### 📝 Usage Notes

* Scripts in this folder are typically executed **within their respective software environments** (e.g., Grasshopper, Revit, OpenStudio CLI).
* They serve as the **interface** for:
    * **Data Generation:** Exporting architectural geometry and data for ML model training and simulation.
    * **Parametric Control:** Driving design variations and parameters through generative algorithms.
    * **Simulation Setup:** Preparing and automating complex building performance simulation runs.
* These tools are essential for establishing the **data pipelines** that feed information between the design tools and the analytical/ML components of the project.

---

### 🚀 Next Steps

* Develop more robust and automated bi-directional links between the design software and the Python ML environment.
* Explore real-time data streaming or API integrations to facilitate dynamic feedback loops for generative design.
* Expand compatibility to other design/simulation platforms if beneficial for specific research questions.
* Document specific setup instructions for each tool's scripts where complex configurations are required.
