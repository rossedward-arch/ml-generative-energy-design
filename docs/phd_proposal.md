# PhD Research Proposal  
**Title**: ML-Driven Generative Design for Energy-Efficient Architecture  
**Applicant**: Ross Edward 
**Proposed Institution**: Edinburgh University   
**Proposed Supervisor**: [To be determined based on alignment with ]  
**Date**: June 2025  

---

## 1. Research Aims and Objectives

The proposed research investigates the integration of machine learning (ML), generative design algorithms, and energy performance simulation to support architects in creating energy-efficient buildings at the early design stage. The primary objectives are:

- To develop predictive models that estimate energy usage and comfort metrics from early-stage design parameters.
- To implement generative optimization techniques that iteratively evolve spatial layouts toward energy and sustainability targets.
- To integrate these models with simulation tools like EnergyPlus and OpenStudio to validate, refine, and retrain performance predictions.
- To explore the application of Passivhaus and Net Zero principles as performance constraints within generative workflows.

---

## 2. Originality and Significance

This research bridges the gap between data-driven architectural performance modeling and early-stage design freedom. While generative design and simulation tools exist independently, their convergence through ML offers a novel approach to automated, performance-informed design. This work is original in that:

- It treats ML not just as a post-analysis tool, but as a core agent of design generation and evaluation.
- It builds an adaptive loop between prediction, optimization, and simulation feedback.
- It addresses design vs. as-built performance gaps by incorporating realistic building operation parameters early.

The research is aligned with UCL Bartlett’s focus on sustainable built environment solutions, digital innovation, and performance-led design.

---

## 3. Research Questions

1. How can supervised machine learning models predict energy performance from early-stage architectural inputs?
2. What generative design strategies best integrate with ML prediction models to optimize building layouts?
3. How can energy simulation feedback be looped into the generative-ML pipeline to improve reliability and performance?
4. Can the resulting workflow consistently generate designs that meet Passivhaus or Net Zero performance thresholds?
5. How can such tools support decision-making for practicing architects, and what barriers exist to implementation?

---

## 4. Research Plan

### Phase 1: Literature & Tool Review
- Review ML applications in architectural design and energy modeling.
- Analyze strengths/limitations of current generative tools (e.g., Grasshopper, DEAP) and simulation engines (EnergyPlus, OpenStudio).

### Phase 2: Data Collection & Processing
- Collect and preprocess geometry, material, weather, and simulation datasets.
- Engineer features such as window-to-wall ratio, compactness, thermal mass indicators, etc.

### Phase 3: ML Model Development
- Train regression models (Random Forest, XGBoost, Neural Networks) to predict EUI, HVAC loads, and comfort.
- Apply dimensionality reduction (PCA), normalization, and encoding.

### Phase 4: Generative Design Integration
- Implement a genetic algorithm using DEAP to evolve spatial configurations.
- Use ML models as surrogate predictors in the optimization loop.
- Introduce constraints based on Passivhaus/Net Zero benchmarks.

### Phase 5: Simulation Feedback Loop
- Validate predicted designs using EnergyPlus/OpenStudio.
- Incorporate feedback into fitness functions and retrain models iteratively.

### Phase 6: Evaluation & Dissemination
- Evaluate performance against benchmark targets.
- Develop a Streamlit or Grasshopper-based UI to demonstrate usability.
- Prepare publications and document reproducible workflows.

---

## 5. Methodology Summary

See [methodology.md](./methodology.md) for the full breakdown.

This research adopts a hybrid approach combining:
- Supervised ML (for prediction)
- Generative optimization (for design evolution)
- Simulation validation (for performance benchmarking)

Tools include:  
Python, Scikit-learn, TensorFlow, DEAP, EnergyPlus, OpenStudio, Grasshopper, Revit, and Ladybug Tools.

---

## 6. Impact Statement

The project has the potential to:

- Enable architects to make informed energy decisions earlier, reducing rework and energy underperformance.
- Contribute open-source tools and datasets that align with Bartlett’s commitment to public knowledge.
- Improve pathways for achieving Passivhaus and Net Zero design targets in mainstream architecture.
- Bridge the designer–engineer divide through accessible interfaces and interpretable feedback.
- Support the UK’s sustainability goals by embedding energy literacy into generative design processes.

---

## 7. Fit with UCL Bartlett

The proposal aligns with the following UCL Bartlett strengths:

- **Bartlett School of Environment, Energy and Resources**: Sustainability, energy modelling, building performance.
- **Institute for Environmental Design and Engineering (IEDE)**: Occupant comfort, environmental simulation, performance gaps.
- **Bartlett School of Architecture**: Computational design, generative workflows, BIM integration.

The interdisciplinary nature also fits UCL’s broader strengths in machine learning, data science, and the Built Environment Faculty.

---

## 8. References (selected)

- Reinhart, C. F., & Davila, C. C. (2016). Urban building energy modeling – A review of a nascent field. *Building and Environment*.
- Nguyen, A. T., Reiter, S., & Rigo, P. (2014). A review on simulation-based optimization methods applied to building performance analysis. *Applied Energy*.
- Tuhus-Dubrow, D., & Krarti, M. (2010). Genetic algorithm based approach to optimize building envelope design for residential buildings. *Building and Environment*.
- Passivhaus Trust. (2023). Passivhaus Planning Package (PHPP).
- UCL Bartlett. (2024). Research themes: Digital innovation and climate-led design.

---

*This document will evolve in parallel with the research. All major components will be published for academic and professional review.*

