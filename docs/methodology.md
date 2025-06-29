# Methodology

This research employs an integrated, multi-stage methodology combining climate-adaptive reinforcement learning (RL), explainable AI (XAI), surrogate modeling, and rigorous validation to optimize generative design for Passivhaus and net-zero buildings in Edinburgh. The stages reflect an iterative process ensuring both technical robustness and practical relevance.

---

## Stage 1: Climate Data Acquisition and Reinforcement Learning Environment Development

### 1.1 Climate Data Processing
- Utilize the UK Met Office’s UKCP18 probabilistic climate projections to model Edinburgh’s future climate scenarios (2030–2050).
- Extract high-resolution hourly meteorological variables including temperature, solar radiation, wind speed and direction, precipitation, and humidity.
- Apply statistical downscaling and uncertainty quantification techniques to generate multiple plausible climate futures, capturing seasonal and extreme weather variability.

### 1.2 RL Environment Design
- Define the **state space** to include multi-dimensional building attributes such as geometry, envelope thermal properties, orientation, window-to-wall ratio, HVAC parameters, renewable energy system specs, and environmental conditions.
- Specify the **action space** as continuous and discrete variables representing design decisions: insulation thickness, glazing type, shading, HVAC controls, renewable deployment, and orientation adjustments.
- Formulate a **multi-objective reward function**:

R = α E_savings + β C_comfort - γ C_embodied + δ R_resilience


where weights \(\alpha, \beta, \gamma, \delta\) balance energy savings, thermal comfort, embodied carbon, and resilience metrics (e.g., passive survivability, grid independence).

### 1.3 RL Algorithm and Training
- Implement advanced RL algorithms such as Proximal Policy Optimization (PPO) and Deep Q-Networks (DQN).
- Employ curriculum learning to progressively introduce environmental complexity, from static climate conditions to stochastic and extreme weather events.
- Incorporate domain-specific constraints (e.g., Passivhaus certification limits) as reward penalties or action clipping.
- Use parallelized simulations and cloud computing for scalable training across multiple climate scenarios and design seeds.

---

## Stage 2: Integration of Explainable Artificial Intelligence (XAI)

- Apply SHAP (SHapley Additive exPlanations) to interpret RL policy decisions, enhancing transparency and stakeholder trust.
- Develop interactive dashboards and reports that visualize trade-offs between insulation, HVAC settings, renewable energy deployment, and resilience measures.
- Conduct user studies with architects, engineers, and policymakers to iteratively refine XAI outputs for clarity and usability.

---

## Stage 3: Surrogate Modeling and Efficiency Improvements

- Develop surrogate machine learning models trained on RL simulation data to accelerate design space exploration.
- Employ dimensionality reduction techniques and feature importance analysis to focus on key design parameters.
- Integrate surrogate models within the RL loop for faster policy updates and real-time design feedback.
- Validate surrogate accuracy against detailed EnergyPlus or TRNSYS simulations.

---

## Stage 4: Validation and Benchmarking

- Use EnergyPlus and TRNSYS to simulate final RL-optimized design candidates under diverse climateios.
- Calibrate digital twin models against historical weather data and monitored post-occupancy performance metrics.
- Benchmark performance against traditional parametric optimization workflows (e.g., Grasshopper + Galapagos/Octopus) and regulatory baselines such as ASHRAE 90.1 and CIBSE TM54.
- Evaluate designs based on:
  - Energy Use Intensity (EUI)
  - Lifecycle embodied and operational carbon
  - Resilience metrics, including thermal autonomy and recovery after outages
- Engage stakeholders in qualitative evaluation through workshops and feedback sessions.

---

## Ethical Considerations and Data Governance

- Ensure transparent and responsible AI use by embedding explainability throughout the design pipeline.
- Maintain compliance with data privacy and sharing agreements for monitored building data accessed via partner organizations.
- Promote open science by releasing code, datasets, and documentation as open-source resources wherever possible.

---

## Summary

This methodology leverages cutting-edge RL and XAI techniques in a climate-adaptive framework, iteratively refined through surrogate modeling and validated via industry-standard simulations and stakeholder engagement. It aims to produce a robust, transparent, and practical generative design tool tailored to Edinburgh’s unique climate and policy context.


