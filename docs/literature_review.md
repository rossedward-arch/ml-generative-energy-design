# Climate-Adaptive AI-Driven Generative Design: A Literature Review

## Introduction

This literature review synthesizes the state of the art in generative design, reinforcement learning (RL), and explainable AI (XAI) within the context of climate-adaptive, high-performance architecture. It critically evaluates how these technologies converge to support the design of buildings that meet Passivhaus and net-zero energy standards. The aim is to establish a foundation for a scalable, interpretable, and adaptive generative design workflow. The review emphasizes the integration of future climate data, surrogate modeling, and performance feedback loops in alignment with emerging priorities in sustainable architecture.

## 1. Overview of Climate-Adapted Generative Design

Generative design systems have gained prominence in architecture due to their ability to automate exploration of large design spaces using algorithmic approaches. These systems often rely on parametric modeling tools such as Grasshopper and Ladybug Tools (Sanguinetti et al., 2019), enabling manipulation of parameters related to geometry, orientation, and material properties.

Recent advances in climate projection data, such as the UK Climate Projections 2018 (UKCP18), provide high-resolution climate scenarios—including temperature, humidity, solar radiation, and wind speed—under various Representative Concentration Pathways (RCPs). These projections can be incorporated into generative frameworks to inform future climate-adaptive strategies (Murphy et al., 2018).

Despite progress, existing generative workflows often fail to effectively incorporate climate variability. This research seeks to bridge that gap by embedding climate-adaptive parameters into the generative process, thus enabling resilient designs that align with Passivhaus and net-zero targets. However, challenges remain in addressing multi-objective optimization and managing the computational cost of evaluating alternatives under multiple climate scenarios. This motivates the use of machine learning and RL to streamline and enhance the generative process.

## 2. Reinforcement Learning in Architectural Optimization

Reinforcement learning enables agents to learn optimal decisions by interacting with an environment to maximize cumulative rewards (Sutton & Barto, 2018). In architectural design, RL allows for sequential, multi-stage decision-making crucial to adaptive, climate-responsive design. RL has demonstrated promise in design space exploration, energy efficiency optimization, and adaptive control (Andriamamonjy et al., 2022).

RL agents iteratively interact with simulation environments to learn strategies. Key challenges include defining effective reward functions that balance competing objectives—such as energy use and occupant comfort—and managing the computational demands of complex simulations. Reward shaping is critical to guide the agent in multi-objective contexts (Wei et al., 2022).

Although RL adoption in architecture faces issues like high-dimensional state spaces and computational expense, techniques such as curriculum learning and multi-objective RL are promising for scalable optimization (Zhang et al., 2020).

## 3. Explainable AI for Transparent Building Performance Models

Explainable AI (XAI) aims to make complex model decisions—such as those made by neural networks—understandable to human users. In building performance modeling, surrogate ML models are frequently used to approximate resource-intensive simulations from tools like EnergyPlus or OpenStudio (Ghiassi & Mahdavi, 2020).

While efficient, these surrogate models are often considered black boxes. XAI tools such as SHAP (SHapley Additive exPlanations) clarify which input variables most influence predictions like energy consumption or thermal comfort, supporting informed and trustworthy design decisions (Lundberg & Lee, 2017).

XAI fosters human-AI collaboration by helping designers validate model logic and align outcomes with domain knowledge, making it a critical element of any AI-enhanced workflow.

## 4. Integration of ML, RL, and XAI in Generative Design

Recent research integrates surrogate ML models with RL agents to speed up optimization, while XAI enhances interpretability of both ML predictions and RL policy decisions. However, fully unified frameworks remain rare.

Some studies embed surrogate models within RL environments to reduce simulation costs (Wang et al., 2021), while others apply SHAP to interpret RL strategies. Despite these developments, ML, RL, and XAI are often applied in isolation. This project proposes a cohesive framework combining these components into a single, integrated generative design pipeline for climate-adaptive architecture.

## 5. Simulation Tools and Digital Twins for Performance Validation

Tools like EnergyPlus and OpenStudio simulate HVAC systems, daylighting, and thermal comfort under varied climate conditions. Ladybug Tools provide a flexible interface for incorporating these simulations into parametric design workflows.

Digital twins—virtual models of real buildings updated with real-time sensor data—enable ongoing performance monitoring and model calibration (Fuller et al., 2020). They offer continuous feedback loops, allowing surrogate models to evolve based on real operational data. Coupling digital twins with XAI further supports transparent and dynamic decision-making throughout a building’s life cycle.

## 6. Conceptual Framework Diagram

```mermaid
graph TD
    A[Climate Projection Data (UKCP18)] --> B[Generative Design Engine]
    B --> C[Reinforcement Learning Agent]
    B --> D[Surrogate ML Models]
    C --> E[Energy Simulation (EnergyPlus)]
    D --> E
    E --> F[XAI Interpretation (SHAP)]
    F --> G[Design Feedback & Adaptation]
    G --> B
    H[Digital Twin Feedback] --> D
```

## 7.Conclusion

This review highlights opportunities for integrating RL, surrogate modeling, and XAI into generative workflows for climate-adaptive architecture. While individual advancements are substantial, unified, scalable frameworks are still lacking. This project proposes a novel methodology that fuses UKCP18 climate data, RL agents, interpretable surrogate models, and digital twin feedback to support optimized, climate-resilient building design. Future work will apply and evaluate this framework through case studies targeting Passivhaus and net-zero goals in Edinburgh.

# References

- Andriamamonjy, A., Saelens, D., & Klein, R. (2022). Reinforcement learning for building energy management: A review. *Energy and Buildings*, 258, 111796.

- Fuller, A., Fan, Z., Day, C., & Barlow, C. (2020). Digital twin: Enabling technologies, challenges and open research. *IEEE Access*, 8, 108952–108971.

- Ghiassi, B., & Mahdavi, A. (2020). Machine learning applications in building performance simulation: A review. *Energy and Buildings*, 227, 110408.

- Lundberg, S. M., & Lee, S.-I. (2017). A unified approach to interpreting model predictions. In *Proceedings of the 31st International Conference on Neural Information Processing Systems* (pp. 4768–4777).

- Murphy, J. M., et al. (2018). UKCP18 land projections: Science report. Met Office Hadley Centre.

- Sanguinetti, A., Abdelrahman, M., Andersen, M., et al. (2019). Human-building interaction: The missing link in building performance simulation. *Buildings and Cities*, 1(1), 287–302.

- Sutton, R. S., & Barto, A. G. (2018). *Reinforcement learning: An introduction* (2nd ed.). MIT Press.

- Wang, Z., Hong, T., & Xu, X. (2021). Reinforcement learning for smart building energy management: A review of recent advances. *Energy and AI*, 6, 100030.

- Wei, T., Wang, Y., & Zhu, Q. (2022). Reward shaping in reinforcement learning: A review. *IEEE Transactions on Neural Networks and Learning Systems*.

- Zhang, K., Yang, Z., & Basar, T. (2020). Multi-agent reinforcement learning: A selective overview of theories and algorithms. *Handbook of Reinforcement Learning and Control*, 321–384.

---

# Appendix A: Supplementary Reading List

This appendix includes foundational and emerging works that deepen understanding of climate-responsive design, ML integration, and explainability in architecture.

### A.1 Climate Adaptation and Energy Simulation

- Attia, S. (2018). *Net Zero Energy Buildings (NZEB): Concepts, Frameworks and Roadmap for Project Analysis and Implementation*. Springer.

- Crawley, D. B., Lawrie, L. K., Winkelmann, F. C., et al. (2001). EnergyPlus: Creating a new-generation building energy simulation program. *Energy and Buildings*, 33(4), 319–331.

- Reinhart, C. F., & Davila, C. C. (2016). Urban building energy modeling – A review of a nascent field. *Building and Environment*, 97, 196–202.

### A.2 Generative and Parametric Design Tools

- Woodbury, R. (2010). *Elements of Parametric Design*. Routledge.

- Gerber, D. J., & Lin, S. H. (2013). Designing in complexity: Simulation, integration, and multidisciplinary design optimization for architecture. *Simulation*, 89(2), 144–161.

### A.3 Reinforcement Learning in Built Environment Applications

- Mnih, V., Kavukcuoglu, K., Silver, D., et al. (2015). Human-level control through deep reinforcement learning. *Nature*, 518(7540), 529–533.

- Yu, Y., et al. (2021). Deep reinforcement learning for building HVAC control: Review and challenges. *Building and Environment*, 187, 107354.

### A.4 Explainable AI and Interpretable Models

- Doshi-Velez, F., & Kim, B. (2017). Towards a rigorous science of interpretable machine learning. *arXiv preprint* arXiv:1702.08608.

- Molnar, C. (2022). *Interpretable Machine Learning: A Guide for Making Black Box Models Explainable*. Available at: [https://christophm.github.io/interpretable-ml-book/](https://christophm.github.io/interpretable-ml-book/)

### A.5 Digital Twins and Data-Driven Calibration

- Negri, E., Fumagalli, L., & Macchi, M. (2017). A review of the roles of digital twin in CPS-based production systems. *Procedia Manufacturing*, 11, 939–948.

- O'Donnell, J., Maile, T., Rose, C., et al. (2013). Transforming BIM to BEM: Generation of building geometry for the NASA Ames Sustainability Base BIM. *IBPSA Building Simulation*.
