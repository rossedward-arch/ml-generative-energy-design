# 1. Literature Review

## 1.1 Climate-Responsive Generative Design

The built environment is a major contributor to global carbon emissions, with early-stage design decisions playing a critical role in determining a building’s long-term energy performance and adaptability to future climates. Generative design has gained traction as a method for exploring complex form-function relationships through algorithmic techniques. Tools like Grasshopper, Ladybug, and Galapagos have enabled evolutionary design processes that optimize for parameters such as daylight, solar gains, and thermal comfort (Nguyen et al., 2014).

However, many generative workflows still rely on fixed climate assumptions or single-objective optimization, lacking adaptability to future climate uncertainties. Attia et al. (2013) critique such approaches as being overly dependent on designer intuition or single-pass simulation, limiting their ability to support performance-informed exploration during conceptual stages.

> **Key Insight**: While generative design methods are maturing, they often fail to address climate resilience and multi-objective trade-offs in a transparent, adaptable way.

**References**:  
- Nguyen, A.T., Reiter, S. & Rigo, P. (2014). *A review on simulation-based optimization methods applied to building performance analysis*. **Applied Energy**, 113, 1043–1058.  
- Attia, S., Hensen, J.L.M., Beltrán, L., & De Herde, A. (2013). *Simulation-based decision support tool for early building design*. **Automation in Construction**, 20, 108–125.

---

## 1.2 Reinforcement Learning in Building Design

Reinforcement Learning (RL) has recently emerged as a promising technique in building control systems, such as HVAC operation and thermal storage optimization (Zhao et al., 2021). Unlike supervised learning, RL agents learn to make sequential decisions by interacting with an environment and receiving feedback through reward signals.

Despite its success in operational controls, RL has not been widely applied to early-stage architectural design, particularly in form-finding or massing processes. Nagpal et al. (2020) explored RL for HVAC control but noted that state-space complexity and training time are critical challenges. Applying RL to conceptual design stages requires reimagining reward structures and integrating design constraints as part of the environment model.

> **Key Insight**: RL has strong potential for exploratory and iterative design processes but remains underexplored in early-stage building geometry and envelope design.

**References**:  
- Nagpal, S., Parameswaran, V., & Jain, R. (2020). *Reinforcement Learning for HVAC Control: Challenges and Opportunities*. **Energy and Buildings**, 207, 109482.  
- Zhao, Y., Li, X., & Wen, J. (2021). *A review of reinforcement learning for building energy optimization*. **Energy and AI**, 4, 100061.

---

## 1.3 Integration of Future Climate Data in Design Tools

Designing for future climate conditions is essential for ensuring building resilience and energy performance over the long term. Weather data generators such as UKCP09 and UKCP18 offer probabilistic weather files representing future climate scenarios, but their use in early design tools is limited (Jenkins et al., 2008). Many performance tools rely on typical meteorological year (TMY) data that do not capture the range of extremes or temporal shifts expected under climate change.

De Wilde (2014) emphasizes the need for dynamic resilience metrics in simulation environments. Without future weather integration, generative models risk creating buildings optimized for obsolete conditions.

> **Key Insight**: Most current generative workflows overlook future climate variability, limiting their usefulness for long-term design resilience.

**References**:  
- Jenkins, D.P., Paszkiewicz, R., & Gibson, G. (2008). *The impact of climate change on energy use in the UK building sector*. **Energy Policy**, 36(12), 4601–4605.  
- de Wilde, P. (2014). *The gap between predicted and measured energy performance of buildings: A framework for investigation*. **Automation in Construction**, 41, 40–49.

---

## 1.4 Energy Simulation and Surrogate Models

Energy simulation tools such as EnergyPlus and OpenStudio provide detailed thermodynamic analyses, essential for performance validation. However, their computational cost poses challenges for iterative generative design. To mitigate this, surrogate models — statistical or machine learning models trained to emulate simulation outputs — have been increasingly used (Evins, 2013).

Common surrogate models include Gaussian Processes, Artificial Neural Networks, and tree-based methods such as XGBoost. While accurate and efficient, these models often act as black boxes, reducing design transparency unless paired with interpretable techniques.

> **Key Insight**: Surrogate models reduce computation time, enabling rapid evaluation, but raise concerns about interpretability and validation.

**References**:  
- Evins, R. (2013). *A review of computational optimization methods applied to sustainable building design*. **Renewable and Sustainable Energy Reviews**, 22, 230–245.  
- Asadi, E., da Silva, M.G., Antunes, C.H., & Dias, L. (2014). *A multi-objective optimization model for building retrofit strategies using EnergyPlus*. **Energy and Buildings**, 81, 444–456.

---

## 1.5 Multi-Objective Optimization in Building Design

Most traditional optimization in building design focuses on single objectives such as minimizing energy use or maximizing daylight. However, sustainable and resilient buildings require balancing multiple objectives, including energy efficiency, thermal comfort, embodied and operational carbon, and resilience to future climate stresses (Zuo & Zhao, 2014).

Multi-objective optimization algorithms allow designers to explore trade-offs and Pareto-optimal solutions, enabling more holistic design decisions (Deb, 2001). Integrating these approaches in generative design workflows remains a technical challenge but is critical for future-ready buildings.

> **Key Insight**: Multi-objective optimization supports balanced, context-sensitive design outcomes beyond simplistic single-metric targets.

**References**:  
- Zuo, J., & Zhao, Z.-Y. (2014). *Green building research–current status and future agenda: A review*. **Renewable and Sustainable Energy Reviews**, 30, 271–281.  
- Deb, K. (2001). *Multi-objective optimization using evolutionary algorithms*. Wiley.

---

## 1.6 Explainable AI (XAI) in Architecture and Building Design

The increasing adoption of AI and ML in architecture necessitates transparency and interpretability to build user trust and support decision-making. Explainable AI (XAI) seeks to make black-box models understandable to humans by providing feature attribution, rule extraction, or visual explanations (Ribeiro et al., 2016).

SHAP (Shapley Additive Explanations) has become a popular XAI method, offering theoretically sound and model-agnostic explanations by distributing the prediction among input features fairly (Lundberg & Lee, 2017). Applications of XAI in building energy modeling and design have demonstrated its potential to clarify complex surrogate models and highlight key drivers of performance (Kim et al., 2021).

> **Key Insight**: XAI techniques like SHAP are essential for bridging the gap between complex ML models and the needs of architects and stakeholders for transparency and trust.

**References**:  
- Ribeiro, M.T., Singh, S., & Guestrin, C. (2016). *"Why should I trust you?": Explaining the predictions of any classifier*. In: Proceedings of the 22nd ACM SIGKDD International Conference on Knowledge Discovery and Data Mining.  
- Lundberg, S.M., & Lee, S.-I. (2017). *A Unified Approach to Interpreting Model Predictions*. In: Advances in Neural Information Processing Systems, 30.  
- Kim, Y., Lee, J., & Cho, Y. (2021). *Explainable AI for building energy performance assessment*. **Building and Environment**, 195, 107766.

---

## 1.7 Stakeholder Engagement and Co-Design Methods

To ensure real-world adoption, generative design tools must be interpretable, interactive, and usable by non-experts. Co-design and participatory methods offer ways to involve stakeholders early in tool development (Bardzell et al., 2012). Think-aloud protocols, dashboard interfaces, and human-in-the-loop strategies are effective for evaluating trust and usability.

Davis et al. (2022) found that explainability and perceived control strongly influence user trust in AI-assisted design environments. This underscores the need for human-centred design in computational tools.

> **Key Insight**: Human factors such as trust, usability, and control are central to tool adoption and should be designed into generative workflows.

**References**:  
- Bardzell, J., Bardzell, S., & Stolterman, E. (2012). *User experience in design practice: Designers’ perspectives*. **Human–Computer Interaction**, 27(5–6), 263–302.  
- Davis, M., Iqbal, T., & Roupé, M. (2022). *Evaluating human trust in AI-assisted design tools*. **Design Studies**, 79, 101065.

---

## 1.8 Digital Twins and Post-Occupancy Validation

Digital twins — dynamic, data-driven models of buildings — have emerged as critical tools for performance validation and long-term system adaptation. Their use in post-occupancy evaluation enables model calibration, anomaly detection, and lifecycle energy analysis (Gao et al., 2022). Proper calibration using statistical metrics such as CV(RMSE) and NMBE ensures that simulated performance aligns with real-world data (Raftery et al., 2011).

In the context of reinforcement learning, digital twins provide a validated environment for training and testing control agents or optimization systems under realistic constraints.

> **Key Insight**: Digital twins support model calibration and validation, strengthening the link between generative intent and built reality.

**References**:  
- Gao, X., Pishdad-Bozorgi, P., & Eastman, C.M. (2022). *Digital Twins in Building Performance Simulation: A review*. **Energy and Buildings**, 261, 111951.  
- Raftery, P., Keane, M.M., & O'Donnell, J. (2011). *Calibrating whole building energy models: An evidence-based methodology*. **Energy and Buildings**, 43(9), 2346–2354.

---

## 1.9 Practical Integration Challenges

Despite advances in RL, surrogate modeling, and explainable AI, integrating these methods into a coherent early-stage design workflow presents significant computational and workflow challenges. Coupling RL agents with detailed simulators like EnergyPlus or TRNSYS involves managing high-dimensional state-action spaces and lengthy training times (Nagpal et al., 2020). Surrogate models alleviate some computational costs but introduce questions of accuracy and validity.

Additionally, building usable interfaces for human-in-the-loop interaction that provide real-time feedback and maintain transparency is non-trivial (Davis et al., 2022). Addressing these integration challenges is critical to realize the practical benefits of advanced AI-driven generative design.

> **Key Insight**: Technical and practical integration challenges underscore the novelty and ambition of this research.

**References**:  
- Nagpal, S., Parameswaran, V., & Jain, R. (2020). *Reinforcement Learning for HVAC Control: Challenges and Opportunities*. **Energy and Buildings**, 207, 109482.  
- Davis, M., Iqbal, T., & Roupé, M. (2022). *Evaluating human trust in AI-assisted design tools*. **Design Studies**, 79, 101065.

---

## 1.10 Summary and Research Gap

Despite significant advances in generative design, simulation, and machine learning, existing approaches lack integration across four key dimensions:

1. **Reinforcement learning** is rarely applied to early-stage design or envelope massing;  
2. **Climate resilience** remains underrepresented in generative workflows;  
3. **Explainability and multi-objective optimization** are absent or underdeveloped in most AI-assisted design tools;  
4. **Stakeholder feedback loops, usability, and validation** are weak or missing.

This research addresses these gaps by proposing a climate-adaptive generative design workflow that integrates RL, simulation-informed surrogate modeling, SHAP-based interpretability, multi-objective optimization, and stakeholder-in-the-loop co-design — grounded in future climate scenarios and validated through digital twins.

---

