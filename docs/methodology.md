## Methodology

This methodology outlines a four-phase research and development workflow, combining **reinforcement learning (RL)**, **energy simulation**, and **explainable AI (XAI)**, with a strong emphasis on performance validation and stakeholder usability. The aim is to create a robust, transparent generative design tool responsive to climate uncertainty and practical architectural constraints.

---

### **Phase 1: Development of a Climate-Adaptive Reinforcement Learning Environment**

**Objective**: Build a generative design environment that enables RL agents to explore building design solutions optimized for future climate scenarios in Scotland.

#### Tasks:

- **Climate Dataset Integration**: Incorporate UKCP18 future weather projections (2030–2050), including temperature, solar radiation, humidity, wind, and precipitation, using EnergyPlus EPW files.

- **Design Variable Encoding**: Define a high-dimensional **state-action space** representing:

  - Building form and orientation
  - Envelope materials and U-values
  - Glazing ratios and shading
  - HVAC system types and control strategies
  - Renewable energy systems (PV, battery storage, etc.)

>The following Python snippet visualizes the key design variables considered in the RL environment’s state-action space.

```python
import matplotlib.pyplot as plt

variables = [
    'Building Form',
    'Orientation',
    'Envelope Materials',
    'Glazing Ratios',
    'Shading',
    'HVAC Systems',
    'Renewable Energy'
]

fig, ax = plt.subplots(figsize=(6,4))
ax.axis('off')
for i, var in enumerate(variables):
    ax.text(0.5, 1 - i*0.15, f"• {var}", fontsize=12, ha='center', va='top')
ax.set_title('Design Variables in RL State-Action Space')
plt.show()
```

- **Reward Function Design**: Formulate a **multi-objective reward function** with tunable weights:

  ```math
  R = \alpha \cdot E_{savings} + \beta \cdot C_{comfort} - \gamma \cdot C_{embodied} + \delta \cdot R_{resilience}
  ```

  Where:

  - \(E_{savings}\): Energy savings vs. baseline
  - \(C_{comfort}\): Occupant thermal comfort score
  - \(C_{embodied}\): Embodied carbon of material choices
  - \(R_{resilience}\): Resilience to extreme events (e.g., passive survivability)

- **Simulation Integration**: Use **EnergyPlus** or **TRNSYS** for performance simulation, with:

  - **Surrogate models** (e.g., Gaussian Process Regression or XGBoost) trained on simulation outputs to reduce computational cost
  - **Parallelized evaluations** via cluster or cloud computing (e.g., AWS/GCP)

---

### **Phase 2: XAI-Enhanced Interpretability Layer**

**Objective**: Integrate explainable AI to make RL decision-making transparent to architects, engineers, and policymakers.

#### Tasks:

- **XAI Integration**:
  - Apply **SHAP** (SHapley Additive exPlanations) to quantify the influence of each design decision on energy, comfort, and carbon outcomes.
  - Embed **context-specific visualizations** to explain complex trade-offs (e.g., better insulation vs. cost vs. embodied carbon).
- **Interactive Interface Development**:
  - Create **dashboards** (using tools like Dash, Streamlit, or React + Plotly) allowing users to:
    - Explore model outputs
    - Adjust trade-off weights in real time
    - Visualize alternative design paths
- **User Testing**:
  - Conduct **co-design workshops** with architects, sustainability consultants, and council officers.
  - Use **think-aloud protocols** and **usability surveys** to refine interpretability, trust, and ease of use.

#### Example: Generating a SHAP Summary Plot with Python

> The following Python snippet demonstrates how to generate a SHAP summary plot for model interpretability.

```python
import shap
import xgboost
import matplotlib.pyplot as plt
import numpy as np

# Load example dataset (e.g., Boston housing)
from sklearn.datasets import load_boston
from sklearn.model_selection import train_test_split

# Load data
X, y = load_boston(return_X_y=True)
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Train an XGBoost model
model = xgboost.XGBRegressor()
model.fit(X_train, y_train)

# Create SHAP explainer and values
explainer = shap.Explainer(model)
shap_values = explainer(X_test)

# Plot summary plot
shap.summary_plot(shap_values, X_test, feature_names=load_boston().feature_names)
plt.show()
```
---

### **Phase 3: Simulation-Driven Generative Design Pipeline**

**Objective**: Deploy and test the full RL-XAI design pipeline.

```mermaid
flowchart LR
    A["UKCP18 Climate Projections"] --> B["RL Agent"]
    B --> C["Design Proposals"]
    C --> D["EnergyPlus Simulations"]
    D --> E["XAI Interpretation (SHAP)"]
    E --> F["User Dashboard + Interactive Feedback"]
    F --> G["Refined Generative Designs"]
```

- Designs are refined iteratively based on simulation feedback and stakeholder input.
- Passivhaus and net-zero performance thresholds are encoded as **hard constraints** (e.g., <15 kWh/m²/yr heating) and **soft optimization targets**.

---

### **Phase 4: Testing, Evaluation, and Validation**

This phase includes rigorous simulation-based validation, benchmarking, and user-centered testing to assess the system's technical performance and stakeholder value.

#### 1. **Simulation-Based Performance Testing**

- Generate building designs using the RL agent and simulate:
  - Annual and peak energy use (EUI)
  - Comfort hours (PMV/PPD or operative temperature)
  - Operational and embodied carbon
  - Resilience metrics (e.g., thermal autonomy, passive survivability)
- Test across **multiple climate scenarios** (baseline, 2030, 2050 UKCP18 datasets).

#### 2. **Benchmarking Against Traditional Tools**

- Compare RL-generated designs with those from parametric tools (e.g., Grasshopper + Galapagos/Octopus).
- Use **identical building typologies and weather files** for fairness.
- Evaluate:
  - Objective performance (EUI, CO₂e, comfort)
  - Time and computational efficiency
  - User trust and perceived control

#### 3. **XAI and Stakeholder Trust Testing**

- Conduct structured interviews and workshops with:
  - Architects
  - Policy advisors
  - Developers
- Use **explanation evaluation metrics** (e.g., Simulatability, Satisfaction, and Trust scales).
- Test dashboard usability and understanding of design trade-offs.

#### 4. **Multi-Objective Optimization Validation**

- Adjust reward function weights (e.g., prioritize carbon vs. comfort) and analyze design shifts.
- Assess:
  - Pareto front quality
  - Stakeholder alignment with outcome preferences
  - Flexibility to adapt to shifting regulatory or budget constraints

#### 5. **Case Studies (New Build + Retrofit)**

- Select two real or representative Scottish buildings:
  - **New build**: social housing, zero-carbon target
  - **Retrofit**: 1950s tenement block
- Apply RL-XAI framework and simulate resulting design strategies
- Evaluate outcomes against:
  - Passivhaus Planning Package (PHPP) metrics
  - Net-zero compliance
  - Stakeholder feedback

#### 6. **Digital Twin Calibration and Validation**

- Where data is available, calibrate simulation models against **real monitored building data** (via ECCI or other partners).
- Validate predictions of energy use, thermal comfort, and peak loads.
- Use statistical methods (e.g., CV(RMSE), NMBE) to measure calibration quality.

---

## Toolchain and Implementation

| Tool                | Purpose                                     |
| ------------------- | ------------------------------------------- |
| Python + OpenAI Gym | RL environment and agent training           |
| EnergyPlus/TRNSYS   | Dynamic simulation of building performance  |
| SHAP + scikit-learn | Explainability and feature attribution      |
| Dash/Streamlit      | Interactive visualization and dashboard UI  |
| GitHub + Docker     | Version control and reproducible containers |

---

## Summary of Improvements Over Existing Methods

| Challenge                      | Solution in This Research                                 |
| ------------------------------ | --------------------------------------------------------- |
| Static climate assumptions     | UKCP18 adaptive weather scenarios                         |
| Black-box AI                   | Integrated SHAP + stakeholder-designed explanations       |
| Narrow design exploration      | High-dimensional, realistic state-action space            |
| Poor generalizability          | Case studies + digital twin validation                    |
| Lack of human-AI collaboration | Real-time interactive dashboard for trade-off exploration |

