# 📂 Data Directory

This folder contains raw and processed datasets used throughout the project, including building geometry, environmental data, and simulation results.

---

## Folder Structure

- `raw/`  
  Original datasets downloaded or collected from external sources.  
  Examples: EPW weather files, building geometry exports (CSV, JSON).

- `processed/`  
  Cleaned and transformed datasets ready for use in machine learning models and simulations.

---

## Data Sources

- EPW weather data obtained from [EnergyPlus Weather Database](https://energyplus.net/weather).
- Architectural geometry exported from Revit and Grasshopper.
- Simulation output data from EnergyPlus/OpenStudio.

---

## Data Usage

- Raw data should never be edited directly; all transformations occur via preprocessing scripts in `src/`.
- Processed data files are version-controlled for reproducibility.
- Metadata describing data provenance and formats can be found in the accompanying README files.

---

## Next Steps

- Expand datasets with additional climate zones and building typologies.
- Incorporate occupant behavior models and real energy consumption data.
- Establish data validation and quality assurance procedures.

