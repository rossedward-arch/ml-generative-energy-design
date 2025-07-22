# 🕹️ Phase 3: ML-Integrated Generative Design (6–12 months)

This phase is dedicated to integrating the machine learning models developed in Phase 2 with parametric and generative design workflows. The primary goal is to leverage ML surrogates to efficiently explore vast architectural design spaces, optimizing for energy performance and other critical building metrics. This integration is a cornerstone for creating intelligent design tools capable of rapid iteration and performance-driven decision-making in the context of climate-adapted, net-zero buildings.

## 🎯 Core Skills & Concepts 

* **Parametric Modeling with Grasshopper & Rhino:** Gained proficiency in creating flexible, rule-based geometric models within Grasshopper (Rhino). This skill is fundamental for defining design variables and generating a multitude of design alternatives that can be systematically evaluated.
* **Surrogate Modeling and ML Model Deployment:** Learned to effectively deploy pre-trained ML models (from Phase 2) as fast-running "surrogates" within design optimization loops. This significantly reduces the computational cost and time associated with high-fidelity energy simulations, enabling real-time feedback during generative processes.
* **Optimization Techniques:** Explored and applied various optimization algorithms, including Genetic Algorithms (GAs) for exploring design permutations and Bayesian Optimization for more sample-efficient search in complex design spaces. Understood how these algorithms leverage ML predictions to guide their search towards optimal solutions.
* **Visualization of Design Iterations and Results:** Developed methods to visually represent the design space, the progression of optimization algorithms, and the trade-offs between multiple performance objectives (e.g., energy use vs. daylighting). This is crucial for human interpretation and decision-making in the design process.
* **Integration of ML Feedback:** Understood how to programmatically connect ML model outputs (predictions) back into the parametric design environment, allowing the generative process to be directly informed and guided by performance insights.

## 🧪 Key Mini-Projects & Exercises 

* **Parametric Model with ML Surrogate Fitness Function:** Created a foundational parametric building model (e.g., a simple shoebox building or facade element) in Grasshopper. Integrated a previously trained ML surrogate model (from Phase 2) to serve as the fitness function for optimization, demonstrating a direct link between design parameters and predicted energy performance.
    * [Link to relevant Grasshopper file and Python script, e.g., `tools/grasshopper_scripts/parametric_energy_opt.gh` and `src/ml_integration/surrogate_fitness.py`](your_github_link_to_file) *(link when build)*
* **Building Orientation or Window Size Optimization:** Implemented a generative design workflow to optimize specific building parameters, such as building orientation or window-to-wall ratio, using the ML surrogate for rapid evaluation of energy performance. This showcased practical application of optimization for early-stage design decisions.
    * [Link to relevant notebook/script, e.g., `notebooks/01_orientation_optimization.ipynb`](your_github_link_to_file)*(link when build)*
* **Simple Generative Design Workflow with ML Integration:** Developed an end-to-end workflow demonstrating how generative algorithms can propose design alternatives, feed parameters to an ML surrogate, and use the predictions to refine subsequent generations.
    * [Link to relevant notebook/script, e.g., `notebooks/02_generative_workflow.ipynb`](your_github_link_to_file)*(link when build)*
* **Pareto Front Visualization for Multi-Objective Optimization:** Visualized the Pareto front for design alternatives, demonstrating the trade-offs between conflicting objectives (e.g., minimizing energy use while maximizing daylighting). This is crucial for understanding the design space and making informed decisions.
    * [Link to relevant visualization script or notebook, e.g., `notebooks/03_pareto_visualization.ipynb`](your_github_link_to_file) *(link when build)*

## 📚 Key Readings & Resources

* *Generative Design: Visualize, Program, and Create with JavaScript in p5.js*, Hartmut Bohnacker et al. – Selected chapters on generative principles and evolutionary algorithms (focus on concepts, not just p5.js).
* Ladybug Tools advanced tutorials and documentation – For in-depth parametric modeling and environmental analysis within Grasshopper.
* Academic papers on surrogate-assisted optimization in architecture, particularly those focusing on building energy performance.
* Resources on Python libraries for optimization (e.g., `DEAP` for genetic algorithms, `Optuna` or `scikit-optimize` for Bayesian optimization) and their integration with design tools.

## 📚 Detailed Learning & Documentation

For a comprehensive breakdown of concepts, code examples, and my daily reflections during this phase, please refer to:

* [**Phase 3 Progress Log**](01_progress_log.md) *(assuming this is the correct path for the progress log within 03_generative_design)*
* [**Notes on Parametric Design**](02_notes_parametric_design.md)
* [**Notes on Generative Algorithms**](03_notes_generative_algorithms.md)

## ➡️ Moving Forward

With the ability to integrate ML models into generative design workflows, the next critical step (Phase 4) will focus on establishing **Simulation-ML Feedback Loops**. This involves automating high-fidelity energy simulations, using their results to retrain and refine the ML surrogates, and exploring the fundamentals of Reinforcement Learning for dynamic design optimization.
