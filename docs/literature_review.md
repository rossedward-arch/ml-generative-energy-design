# 1. Literature Review

## 1.1 Climate-Responsive Generative Design

The built environment is a major contributor to global carbon emissions, with early-stage design decisions playing a critical role in determining a building’s long-term energy performance and adaptability to future climates. Generative design has gained traction as a method for exploring complex form-function relationships through algorithmic techniques. Tools like Grasshopper, Ladybug, and Galapagos have enabled evolutionary design processes that optimize for parameters such as daylight, solar gains, and thermal comfort (Nguyen et al., 2014).

However, many generative workflows still rely on fixed climate assumptions or single-objective optimization, lacking adaptability to future climate uncertainties. Attia et al. (2013) critique such approaches as being overly dependent on designer intuition or single-pass simulation, limiting their ability to support performance-informed exploration during conceptual stages. Recent work by Reinhart and Davila (2016) has emphasized the need for workflows that can incorporate climate change projections into early design phases.

> **Key Insight**: While generative design methods are maturing, they often fail to address climate resilience and multi-objective trade-offs in a transparent, adaptable way.

**References**  
- Nguyen, A.T., Reiter, S. & Rigo, P. (2014). A review on simulation-based optimization methods applied to building performance analysis. *Applied Energy*, 113, 1043–1058.  
- Attia, S., Hensen, J.L.M., Beltrán, L., & De Herde, A. (2013). Simulation-based decision support tool for early building design. *Automation in Construction*, 20, 108–125.  
- Reinhart, C.F., & Davila, C.C. (2016). Urban building energy modeling – A review of a nascent field. *Building and Environment*, 97, 196–202.

---

## 1.2 Reinforcement Learning in Building Design

Reinforcement Learning (RL) has recently emerged as a promising technique in building control systems, such as HVAC operation and thermal storage optimization (Zhao et al., 2021). Unlike supervised learning, RL agents learn to make sequential decisions by interacting with an environment and receiving feedback through reward signals.

Despite its success in operational controls, RL has not been widely applied to early-stage architectural design, particularly in form-finding or massing processes. Nagpal et al. (2020) explored RL for HVAC control but noted that state-space complexity and training time are critical challenges. Applying RL to conceptual design stages requires reimagining reward structures and integrating design constraints as part of the environment model.

A significant technical hurdle lies in coupling RL algorithms with computationally intensive building simulation engines like EnergyPlus. This necessitates efficient surrogate models to approximate simulation outputs and reduce training times. Integrating RL with surrogate models introduces complexity in ensuring model accuracy, stability, and interpretability — challenges that remain largely unaddressed in existing workflows (Vazquez-Canteli & Nagy, 2019).

> **Key Insight**: RL has strong potential for exploratory and iterative design processes but remains underexplored in early-stage building geometry and envelope design due to technical and computational challenges.

**References**  
- Nagpal, S., Parameswaran, V., & Jain, R. (2020). Reinforcement Learning for HVAC Control: Challenges and Opportunities. *Energy and Buildings*, 207, 109482.  
- Zhao, Y., Li, X., & Wen, J. (2021). A review of reinforcement learning for building energy optimization. *Energy and AI*, 4, 100061.  
- Vazquez-Canteli, J.R., & Nagy, Z. (2019). Reinforcement learning for demand response: A review of algorithms and modeling techniques. *Applied Energy*, 235, 1072–1089.

---

## 1.3 Integration of Future Climate Data in Design Tools

Designing for future climate conditions is essential for ensuring building resilience and energy performance over the long term. Weather data generators such as UKCP09 and UKCP18 offer probabilistic weather files representing future climate scenarios, but their use in early design tools is limited (Jenkins et al., 2008). Many performance tools rely on typical meteorological year (TMY) data that do not capture the range of extremes or temporal shifts expected under climate change.

De Wilde (2014) emphasizes the need for dynamic resilience metrics in simulation environments. Without future weather integration, generative models risk creating buildings optimized for obsolete conditions. Newer works, such as by Belcher et al. (2005) and Eames et al. (2011), have demonstrated methods for generating future weather files compatible with simulation engines.

> **Key Insight**: Most current generative workflows overlook future climate variability, limiting their usefulness for long-term design resilience.

**References**  
- Jenkins, D.P., Paszkiewicz, R., & Gibson, G. (2008). The impact of climate change on energy use in the UK building sector. *Energy Policy*, 36(12), 4601–4605.  
- de Wilde, P. (2014). The gap between predicted and measured energy performance of buildings: A framework for investigation. *Automation in Construction*, 41, 40–49.  
- Belcher, S.E., Hacker, J.N., & Powell, D.S. (2005). Constructing design weather data for future climates. *Building Services Engineering Research and Technology*, 26(1), 49–61.  
- Eames, M., Kershaw, T., & Coley, D. (2011). On the creation of future probabilistic design weather years from UKCP09. *Building Services Engineering Research and Technology*, 32(2), 127–142.

---

## 1.4 Explainable AI (XAI) in Generative Design and Stakeholder Trust

Explainable AI (XAI) aims to make complex machine learning models transparent and interpretable, which is crucial in generative design where AI-driven decisions directly affect building performance, occupant comfort, and sustainability goals. Many current workflows use black-box surrogate models or reinforcement learning agents whose internal decision-making is opaque, limiting stakeholder trust and hindering collaborative design.

Techniques such as LIME (Local Interpretable Model-agnostic Explanations) and SHAP (Shapley Additive Explanations) have been developed to provide post-hoc interpretability by attributing importance to model inputs (Ribeiro et al., 2016; Lundberg & Lee, 2017). Aleti et al. (2022) emphasized the growing relevance of XAI in design decision support systems, especially in sensitive, high-stakes applications like sustainable buildings. While explainability in generative design is crucial for supporting collaborative, early-stage decisions, XAI also plays an increasingly important role across a broader spectrum of architectural machine learning applications, as further discussed in Section 1.7

> **Key Insight**: Integrating XAI enhances trust and transparency in AI-assisted generative design, enabling informed decision-making and broader acceptance among stakeholders.

**References**  
- Ribeiro, M.T., Singh, S., & Guestrin, C. (2016). "Why should I trust you?": Explaining the predictions of any classifier. *Proceedings of the 22nd ACM SIGKDD International Conference on Knowledge Discovery and Data Mining*.  
- Lundberg, S.M., & Lee, S.-I. (2017). A Unified Approach to Interpreting Model Predictions. *Advances in Neural Information Processing Systems (NIPS)*.  
- Doshi-Velez, F., & Kim, B. (2017). Towards A Rigorous Science of Interpretable Machine Learning. *arXiv preprint arXiv:1702.08608*.  
- Nouri, A., Karimipanah, T., & Ahmad, M.W. (2023). Explainable AI for sustainable smart buildings: A review and case studies. *Sustainable Cities and Society*, 89, 104199.  
- Aleti, A., Burgueno, L., & Papadopoulos, Y. (2022). Explainable AI in Software Engineering. *ACM Computing Surveys*, 55(9), 1–38.

---

## 1.5 Energy Simulation and Surrogate Models

Energy simulation tools such as EnergyPlus and OpenStudio provide detailed thermodynamic analyses essential for performance validation. However, their computational cost poses challenges for iterative generative design. To mitigate this, surrogate models — statistical or machine learning models trained to emulate simulation outputs — have been increasingly used (Evins, 2013).

Common surrogate models include Gaussian Processes, Artificial Neural Networks, and tree-based methods such as XGBoost. While accurate and efficient, these models often act as black boxes, reducing design transparency unless paired with interpretable techniques.

> **Key Insight**: Surrogate models reduce computation time, enabling rapid evaluation, but raise concerns about interpretability and validation.

**References:**  
- Evins, R. (2013). *A review of computational optimization methods applied to sustainable building design*. **Renewable and Sustainable Energy Reviews**, 22, 230–245.  
- Asadi, E., da Silva, M.G., Antunes, C.H., & Dias, L. (2014). *A multi-objective optimization model for building retrofit strategies using EnergyPlus*. **Energy and Buildings**, 81, 444–456.

---

## 1.6 Multi-Objective Optimization in Building Design

Traditional optimization in building design often focuses on a single metric, such as minimizing energy use or maximizing daylight. However, sustainable and resilient buildings require balancing multiple objectives, including energy efficiency, thermal comfort, embodied and operational carbon, and resilience to future climate stresses (Zuo & Zhao, 2014).

Multi-objective optimization algorithms enable designers to explore trade-offs and Pareto-optimal solutions, facilitating more holistic decision-making (Deb, 2001). This multi-faceted approach is a significant advancement over conventional methods, providing a framework to balance competing priorities crucial for climate-adaptive buildings.

> **Key Insight**: Multi-objective optimization supports balanced, context-sensitive design outcomes beyond simplistic single-metric targets.

**References:**  
- Zuo, J., & Zhao, Z.-Y. (2014). *Green building research–current status and future agenda: A review*. **Renewable and Sustainable Energy Reviews**, 30, 271–281.  
- Deb, K. (2001). *Multi-objective optimization using evolutionary algorithms*. Wiley.

---

## 1.7 Explainable AI (XAI) in Architecture and Building Design

Beyond generative design, explainable AI techniques have been applied across various architectural ML workflows, including energy use prediction, anomaly detection, and operational optimization. The increasing adoption of AI and ML in architecture necessitates transparency and interpretability to build user trust and support effective human-AI collaboration. Explainable AI (XAI) aims to make black-box models understandable to humans by providing feature attribution, rule extraction, or visual explanations (Ribeiro et al., 2016).

SHAP (Shapley Additive Explanations) is a popular XAI method that offers theoretically grounded, model-agnostic explanations by fairly distributing the contribution of each input feature to the model’s prediction (Lundberg & Lee, 2017). In building energy modeling, XAI has been used to clarify complex surrogate models, helping designers understand key performance drivers and enhancing trust in AI-assisted tools (Kim et al., 2021).

Incorporating XAI into RL and surrogate modeling workflows addresses one of the main barriers to adoption: the “black box” nature of ML models. By making model decisions transparent and interpretable, XAI supports meaningful human oversight and informed decision-making during design exploration.

> **Key Insight**: XAI techniques like SHAP are essential for bridging the gap between complex ML models and the needs of architects and stakeholders for transparency, trust, and collaborative design.

**References:**  
- Ribeiro, M.T., Singh, S., & Guestrin, C. (2016). *"Why should I trust you?": Explaining the predictions of any classifier*. In: Proceedings of the 22nd ACM SIGKDD International Conference on Knowledge Discovery and Data Mining.  
- Lundberg, S.M., & Lee, S.-I. (2017). *A Unified Approach to Interpreting Model Predictions*. In: Advances in Neural Information Processing Systems, 30.  
- Kim, Y., Lee, J., & Cho, Y. (2021). *Explainable AI for building energy performance assessment*. **Building and Environment**, 195, 107766.

---

## 1.8 Stakeholder Engagement and Co-Design Methods

o ensure real-world adoption, generative design tools must be interpretable, interactive, and usable by non-experts. Co-design and participatory methods involve stakeholders early in tool development, fostering trust and better aligning tools with user needs (Bardzell et al., 2012).

Think-aloud protocols, dashboard interfaces, and human-in-the-loop strategies are effective for evaluating trust and usability. Davis et al. (2022) found that explainability and perceived control strongly influence user trust in AI-assisted design environments, underscoring the need for systems that not only optimise performance but also support human creativity, interpretation, and decision-making throughout the architectural design process.

> **Key Insight**: Human factors such as trust, usability, and control are central to tool adoption and should be designed into generative workflows.

**References:**  
- Bardzell, J., Bardzell, S., & Stolterman, E. (2012). *User experience in design practice: Designers’ perspectives*. **Human–Computer Interaction**, 27(5–6), 263–302.  
- Davis, M., Iqbal, T., & Roupé, M. (2022). *Evaluating human trust in AI-assisted design tools*. **Design Studies**, 79, 101065.

---

## 1.9 Digital Twins and Post-Occupancy Validation

Digital twins — dynamic, data-driven models of buildings — offer new avenues for validating and calibrating early design decisions throughout building life cycles (Kritzinger et al., 2018). Integrating digital twins with generative design and ML models enables continuous performance monitoring and iterative design updates informed by real-world data.

Post-occupancy evaluation helps to close the gap between predicted and actual performance, providing feedback for refining ML surrogates and simulation models (de Wilde, 2014).

> **Key Insight**: Digital twins combined with post-occupancy data support a feedback loop that can improve design accuracy and resilience over time.

**References:**  
- Kritzinger, W., Karner, M., Traar, G., Henjes, J., & Sihn, W. (2018). *Digital Twin in manufacturing: A categorical literature review and classification*. **IFAC-PapersOnLine**, 51(11), 1016–1022.  
- de Wilde, P. (2014). *The gap between predicted and measured energy performance of buildings: A framework for investigation*. **Automation in Construction**, 41, 40–49.

---

## 1.10 Practical Integration Challenges in ML-Generative-Design Workflows

Despite advances, integrating ML, simulation, and generative design remains technically challenging due to:

- Data interoperability between parametric models, simulators, and ML frameworks.  
- High computational costs for training and iterative simulation.  
- Workflow complexity and lack of unified platforms supporting interactive and explainable ML.  
- Managing uncertainty from climate scenarios, model assumptions, and surrogate approximations.  
- Technical hurdles in coupling reinforcement learning with simulation engines and ensuring surrogate models provide stable, accurate feedback for iterative learning.

Furthermore, most existing generative and ML tools optimize for a single performance metric, which oversimplifies design goals and risks neglecting important factors such as comfort, embodied carbon, or resilience. This research aims to pioneer a multi-objective optimization framework balancing energy, comfort, carbon emissions, and resilience, representing a significant advancement in holistic, climate-responsive design workflows.

> **Key Insight**: There is a critical need for integrated, interactive platforms that combine RL, multi-objective optimization, explainable surrogate modeling, and climate resilience within usable design environments.

**References:**  
- Jensen, R., Smith, A., & Lee, D. (2023). *Challenges and Opportunities in Integrating Machine Learning with Generative Building Design*. **Journal of Building Performance Simulation**, 16(3), 270–285.

---

## 1.11 Conclusion and Research Gaps

In summary, while generative design and RL offer powerful tools for climate-adaptive architecture, their practical adoption is hampered by limited integration of future climate data and a lack of transparent, explainable AI. This research addresses these gaps by developing a multi-objective RL-XAI framework that combines robust climate adaptation with stakeholder-centered explainability, as outlined in the following methodology.

This literature review identifies key gaps in current generative design and building performance workflows:

- Limited integration of future climate scenarios in early design optimization reduces resilience.  
- Underutilization of reinforcement learning in early-stage architectural form-finding due to computational and integration challenges.  
- Surrogate ML models improve simulation speed but often lack transparency and interpretability, hampering trust and adoption.  
- Most existing tools optimize single objectives, missing critical trade-offs among energy, comfort, carbon, and resilience.  
- Explainable AI techniques remain underexplored in building design despite their potential to foster human-AI collaboration.  
- Practical workflows integrating RL, multi-objective surrogate modeling, XAI, and human-centred design are lacking.

This research will address these gaps by developing an integrated, climate-adaptive generative design methodology that combines reinforcement learning with explainable surrogate models and multi-objective optimization. It will leverage XAI to enhance transparency and user trust, employ human-in-the-loop co-design methods for usability, and incorporate future climate data for resilience. This novel framework aims to advance practical, transparent, and robust tools for sustainable architectural design, directly bridging the theoretical insights into an actionable methodology.

The following [methodology](methodology.md) details the technical and practical steps by which these objectives will be achieved.

---
