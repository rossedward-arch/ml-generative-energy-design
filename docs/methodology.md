## Methodology

This research employs an integrated approach combining reinforcement learning (RL), explainable AI (XAI), and simulation-based validation to develop a climate-adaptive generative design framework for Passivhaus and net-zero buildings in Edinburgh. The methodology is divided into four key phases:

---

### Phase 1: Climate-Adaptive Reinforcement Learning Environment

- **Climate Data Integration:** Utilize UKCP18 probabilistic weather projections to represent future climate scenarios for Edinburgh (2030–2050). This ensures the RL agent adapts to evolving temperature, rainfall, wind, and solar radiation patterns.

- **State and Action Space Definition:**  
  - **State variables** include building geometry, envelope properties, orientation, HVAC system settings, and renewable energy configurations.  
  - **Action space** allows modification of these parameters to explore design variations.

- **Reward Function Design:** Multi-objective reward balancing:  
  \[
  R = \alpha \times E_{savings} + \beta \times C_{comfort} - \gamma \times C_{embodied} + \delta \times R_{resilience}
  \]  
  where:  
  - \(E_{savings}\) = operational energy savings,  
  - \(C_{comfort}\) = occupant thermal comfort metrics,  
  - \(C_{embodied}\) = embodied carbon footprint,  
  - \(R_{resilience}\) = resilience to extreme weather events,  
  and \(\alpha, \beta, \gamma, \delta\) are tunable weights optimized during training.

- **Training:** Employ deep reinforcement learning algorithms (e.g., Proximal Policy Optimization) to iteratively improve design policies across stochastic climate scenarios, enabling adaptive, robust building designs.

---

### Phase 2: Explainable AI Integration

- **SHAP Analysis:** Apply SHapley Additive exPlanations (SHAP) to interpret RL agent decisions, quantifying the contribution of each design parameter to the reward outcomes.

- **Interactive Visualization:** Develop dashboards to visualize trade-offs and sensitivities, allowing stakeholders to explore how design choices impact energy efficiency, comfort, carbon, and resilience.

- **Stakeholder Engagement:** Incorporate user feedback loops with designers and policymakers to refine explainability features, ensuring transparency and trust.

---

### Phase 3: Generative Design Pipeline

- **Parametric Model Integration:** Implement parametric building models in Grasshopper or similar platforms, linked to the RL environment for seamless design iteration.

- **Design Constraints:** Embed Passivhaus and net-zero certification criteria as hard and soft constraints within the RL environment to guide feasible solution generation.

- **Optimization Loop:** RL agent proposes designs; XAI tools analyze and explain; stakeholders evaluate and provide input; the agent refines design strategies accordingly.

---

### Phase 4: Validation and Benchmarking

- **Simulation Validation:** Export final candidate designs for detailed energy and comfort simulations using EnergyPlus or TRNSYS to verify RL predictions.

- **Digital Twin Calibration:** Calibrate simulation models against monitored post-occupancy data and historical weather records to ensure real-world accuracy.

- **Benchmarking:** Compare RL-generated designs against:  
  - Traditional parametric optimization workflows (e.g., Grasshopper + Galapagos/Octopus),  
  - Established standards and baselines such as ASHRAE 90.1 and CIBSE TM54.

- **Performance Metrics:** Evaluate based on:  
  - Energy Use Intensity (EUI),  
  - Lifecycle carbon emissions (embodied + operational),  
  - Resilience metrics including thermal autonomy and recovery times after outages.

---

### Tools and Technologies

- **Programming Languages:** Python (for RL and XAI implementations), Rhino/Grasshopper (for parametric modeling).
- **RL Frameworks:** Stable Baselines3, TensorFlow, or PyTorch.
- **Simulation Software:** EnergyPlus, TRNSYS.
- **Data Sources:** UKCP18 climate projections, local building performance monitoring datasets.
- **Visualization:** SHAP libraries, Plotly/Dash for interactive dashboards.

---

### Ethical and Data Considerations

- Ensure open data usage policies by relying on publicly available climate data (UKCP18) and anonymized monitored building datasets.
- Promote transparency through explainability to address ethical concerns related to AI-driven design decisions.
- Engage with local stakeholders to align research objectives with community needs and regulatory frameworks.

---

This methodology ensures a rigorous, transparent, and adaptive design optimization process that responds to the complexities of future climate risks and sustainable building performance targets in Edinburgh.
