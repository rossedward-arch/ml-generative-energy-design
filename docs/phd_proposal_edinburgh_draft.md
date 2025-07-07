# CDT PhD Proposal Summary  
**EPSRC Centre for Doctoral Training in Machine Learning Systems**  
**University of Edinburgh – Bayes Centre**  

## Title  
Reinforcement Learning and Explainable AI for Climate-Adaptive Generative Design of Net-Zero and Passivhaus Buildings  

## Abstract  
This project develops a machine learning (ML) system that integrates reinforcement learning (RL) and explainable AI (XAI) into a generative design framework for energy- and climate-optimized buildings. We aim to build a sample-efficient RL agent capable of navigating sparse, multi-objective design spaces by interfacing with energy simulation engines (e.g., EnergyPlus) and surrogate models. The system will dynamically adapt to UKCP18-based future climate scenarios while adhering to Passivhaus and Net-Zero Energy (NZE) constraints.  

The RL agent is paired with XAI tools (e.g., SHAP, LIME) to provide transparency and stakeholder-aligned decision support via an interactive design dashboard. By treating the simulation-based generative design process as a high-dimensional sequential decision-making problem, this research contributes novel RL reward-shaping, transfer learning for climate generalization, and hybrid surrogate–simulation co-models.  

This project will also contribute to ML systems design by demonstrating RL + XAI integration in a co-simulation environment with real-world constraints, performance feedback, and human-in-the-loop design evaluation.  

## Research Objectives  
1. **Design a Reinforcement Learning framework** for guiding architectural generative design toward energy performance, comfort, and climate resilience goals.  
2. **Develop hybrid ML–simulation surrogate models** to reduce evaluation time in design optimization loops.  
3. **Implement explainability techniques (SHAP, LIME, counterfactuals)** to increase transparency in design recommendations.  
4. **Construct a multi-modal reward system** integrating energy, cost, emissions, and thermal comfort with adaptive weights.  
5. **Validate the system with UKCP18 climate data** and apply it to Edinburgh-specific Net-Zero and Passivhaus case studies.  

## Machine Learning Systems Contribution  
- **Reinforcement Learning for Sparse, Delayed-Reward Spaces**: Design space exploration is high-dimensional, non-convex, and involves delayed feedback from simulation. This provides a testbed for RL methods under real-world complexity.  
- **Sample Efficiency via Surrogate-Augmented RL**: We will fuse ML-based energy predictors with high-fidelity simulations to accelerate training while maintaining generalizability.  
- **Human-AI Collaboration**: Incorporation of XAI and co-design interfaces advances human-in-the-loop learning systems.  
- **Climate-Aware Transfer Learning**: The system will be validated under multiple UKCP18 climate trajectories, allowing RL generalization across climate zones.  

## Interdisciplinary and Societal Relevance  
Buildings contribute over 35% of global emissions. Climate adaptation in architecture is a growing concern, especially in the UK. This system has the potential to support designers, engineers, and policymakers with interpretable ML-assisted design workflows, accelerating the transition to net-zero energy buildings.

## Supervisory Fit  
- **Informatics**: Prof. Subramanian Ramamoorthy, Dr. Stefano V. Albrecht (Reinforcement Learning, Sequential Decision-Making)  
- **Engineering/Architecture** (co-supervision): Dr. Julio Bros-Williamson (ECCI), Prof. Dimitrios Rovas (Energy Simulation, Building Physics)  

## Timeline (4-Year CDT Format)  

| Year | Focus | Outputs |
|------|-------|---------|
| **1** | CDT modules (RL, XAI, systems design); literature review; prototyping; define use case & metrics | Technical review, mini-projects, simulation sandbox |
| **2** | Develop RL agent + surrogate simulation loop; reward tuning; integrate UKCP18 datasets | Proof-of-concept RL system; early evaluation |
| **3** | Implement XAI module (SHAP, counterfactuals); dashboard UI; human-in-the-loop testing | Usability study, academic paper draft |
| **4** | Generalization to new climates; full simulation runs; post-occupancy benchmarking; write-up | Final thesis; 1–2 publications; open-source toolkit |

## Tools & Technologies  
- **ML**: PyTorch, Stable-Baselines3, SHAP, Optuna  
- **Simulation**: EnergyPlus, OpenStudio, TRNSYS  
- **Data**: UKCP18, EPC database, Passivhaus verification models  
- **UI**: Streamlit, Dash (for XAI dashboard)  
- **Deployment**: Docker, HPC/Cluster for parallel RL rollouts  

## Licensing and Impact  
- The project will be open-source (MIT License) and support reproducibility.  
- Potential for use in regulatory simulation (e.g., SAP, PHPP tools), city-scale carbon modeling, and sustainable housing initiatives.  
