# PhD Research Proposal

## Title  
**Integrated Reinforcement Learning and Explainable AI for Climate-Adapted Generative Design of Passivhaus and Net-Zero Buildings**

## Abstract  
This research proposes a novel framework that integrates reinforcement learning (RL) and explainable artificial intelligence (XAI) to optimize climate-adaptive generative design for ultra-low-energy buildings in Edinburgh. By focusing on Scotland’s net-zero targets and shifting climate patterns, the study aims to deliver transparent, policy-aligned design tools tailored for both retrofit and new-build scenarios. The project aligns with the University of Edinburgh’s expertise in AI, sustainable architecture, and urban informatics.

---

## 1. Background and Research Gap

Buildings contribute approximately 40% of global carbon emissions. Standards such as **Passivhaus** and **Net-Zero Energy Buildings (NZEBs)** are critical to reducing operational and embodied energy, especially in temperate and coastal cities like Edinburgh. However, current generative design tools face three major limitations:

- **Climate Adaptation**: Most rely on historical or static climate files, which fail to capture future weather variability (e.g. UKCP18 projections showing increased rainfall and wind extremes).
- **Decision Transparency**: Black-box AI methods erode stakeholder confidence in automated design outcomes.
- **Dynamic Optimization**: Existing workflows rarely integrate occupant behavior, dynamic weather, and energy-grid interaction holistically.

**Research Gap**: While reinforcement learning has shown potential in control systems and urban-scale energy optimization, its integration with building design tools—particularly when paired with explainable AI—is underexplored.

---

## 2. Research Aims

This project aims to develop an **integrated RL-XAI framework** for climate-adaptive building design that:

- Dynamically adapts to **Edinburgh’s future climate** (2030–2050), including precipitation, wind, and temperature variability.
- Optimizes for **energy efficiency, occupant comfort, resilience**, and **carbon reduction** simultaneously.
- Produces interpretable, policy-relevant design outputs for **Passivhaus** and **net-zero operational energy** targets.

---

## 3. Methodology

### Phase 1: Climate-Adaptive Reinforcement Learning

**RL Environment Design**  
- **State Space**: Includes dynamic climate inputs (UKCP18 future weather files), occupancy schedules, and real-time indoor/outdoor thermal conditions.
- **Action Space**: Configurable parameters include:
  - Building form and orientation  
  - Envelope performance (insulation, airtightness)  
  - Glazing ratio and shading  
  - Renewable energy systems  
  - HVAC system parameters

**RL Algorithm**  
- **Proximal Policy Optimization (PPO)** or **Soft Actor-Critic (SAC)** will be used to support continuous action spaces and multi-objective tuning.

**Reward Function**  
\[
R = \alpha \cdot E_{savings} + \beta \cdot C_{comfort} - \gamma \cdot Carbon_{embodied} + \delta \cdot Resilience_{extreme}
\]
- Coefficients \((\alpha, \beta, \gamma, \delta)\) will be tuned using **multi-objective Bayesian optimization** or **NSGA-II**.

### Phase 2: Explainable AI (XAI) Integration

**Goal**: Improve transparency and stakeholder understanding of RL-based design decisions.

- Implement **SHAP** (SHapley Additive exPlanations) to interpret surrogate models trained on RL policies.
- Explore additional methods:
  - **Counterfactual path explanations** for building form changes.
  - **Trajectory summarization** to visualize design evolution.
- Generate **human-readable reports** that highlight:
  - Trade-offs (e.g. insulation thickness vs. renewable ROI)
  - Strategies for flood/wind resilience (e.g. coastal façades, wind buffers)

### Phase 3: Generative Design Pipeline

```mermaid
graph LR
A[Future Climate Data (UKCP18)] --> B(RL Agent)
B --> C{Multi-objective Design Space}
C --> D[Passivhaus Compliance Check]
C --> E[Net-Zero Energy Check]
D & E --> F[XAI Interpretability Layer]
F --> G[Generative Design Output]
```
## Phase 4: Validation

- **Simulation Tools**:  
  - EnergyPlus or TRNSYS to model final design candidates.

- **Digital Twin Calibration**:  
  - Validate against historical weather data and monitored post-occupancy performance.

- **Benchmarking Against**:
  - Traditional parametric optimization (e.g. Grasshopper + Galapagos/Octopus)
  - Regulatory baselines such as **ASHRAE 90.1** and **CIBSE TM54**

- **Evaluation Metrics**:
  - **Energy Use Intensity (EUI)**
  - **Lifecycle Carbon** (embodied + operational)
  - **Resilience Metrics**:
    - Thermal autonomy
    - Recovery time after power loss or environmental disruption

---

## 4. Design and Certification Criteria

| **Standard**   | **Key Metrics**                                                                 |
|----------------|----------------------------------------------------------------------------------|
| **Passivhaus** | Airtightness (<0.6 ACH), U-values ≤ 0.15 W/m²K, heating demand <15 kWh/m²/year   |
| **Net-Zero**   | Annual EUI < 35 kWh/m²/year, on-site renewables coverage ≥100%                   |
| **Resilience** | Operable windows, passive cooling, thermal mass, storm- and flood-resistant façades |

> These criteria will be embedded as **soft/hard constraints** within the RL environment.

---

## 5. Expected Outcomes

- **Open-source toolkit**:  
  A Python-based, Edinburgh-specific climate-adapted generative design library.

- **XAI-informed policy guidelines**:  
  Interactive decision dashboards and reports for local authorities and stakeholders.

- **Academic impact**:  
  Peer-reviewed validation demonstrating ≥30% energy performance improvements compared to ASHRAE 90.1 baselines.

---

## 6. Alignment with the University of Edinburgh

### Research Environment

- **AI/ML Strengths**:  
  - Bayes Centre’s reinforcement learning laboratories  
  - School of Informatics expertise in deep learning and decision systems

- **Sustainable Architecture**:  
  - Edinburgh Climate Change Institute (ECCI)  
  - School of Architecture and Landscape Architecture (ESALA)

### Local Relevance

Focus areas include:

- Coastal flooding resilience (Leith, Granton)
- Heritage retrofit challenges (e.g. tenement housing in the Old Town)
- Integration with district heating networks and smart grids

### Funding Alignment

- **EPSRC: AI for Net-Zero**  
- **Scotland’s Climate Emergency Fund**  
- **University of Edinburgh’s strategic plan** on AI, sustainability, and climate leadership

---

## 7. Implementation Timeline

| **Year** | **Activities**                                                                 |
|----------|----------------------------------------------------------------------------------|
| Year 1   | Develop RL environment; design reward function; integrate future weather data    |
| Year 2   | Implement XAI tools; conduct new-build and retrofit case studies in Edinburgh    |
| Year 3   | Validate design solutions; deploy toolkit; publish open-access policy guidance   |

---

## References (Selected)

1. UK Met Office (2021). *UKCP18 Climate Projections*.  
2. Gao, Y., et al. (2023). *Reinforcement Learning for Building Energy Optimization: A Review*. *Applied Energy*.  
3. Ribeiro, M.T., et al. (2016). *“Why Should I Trust You?”: Explaining the Predictions of Any Classifier*. *KDD*.  
4. O’Donnell, J., et al. (2022). *AI-Assisted Design for NZEB Retrofits*. *Building and Environment*.  
5. Lundberg, S., & Lee, S.I. (2017). *A Unified Approach to Interpreting Model Predictions*. *NIPS* (SHAP).

---

## Conclusion

This research bridges cutting-edge AI methods with climate-resilient building design, empowering Scotland’s transition to net-zero through transparent, adaptive, and high-performance architecture. By integrating reinforcement learning and explainability into generative design, the project positions the University of Edinburgh at the forefront of sustainable, AI-driven innovation in the built environment.


*This document will evolve in parallel with the research. All major components will be published for academic and professional review.*

