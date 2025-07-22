# ⚙️ Phase 2: Machine Learning for Energy Prediction (3–6 months)

This phase is dedicated to building and applying core machine learning skills, specifically focusing on supervised learning methods, to develop predictive models for building energy performance. Mastering these techniques is essential for creating efficient surrogate models that can significantly accelerate the iterative design and optimization processes in later phases of the PhD research.

## 🎯 Core Skills & Concepts 

* **Supervised Learning Algorithms:** Gained a solid understanding and practical experience with fundamental regression algorithms such as Linear Regression, Decision Trees, and Random Forests, which are highly applicable for predicting continuous energy values (e.g., kWh/year, peak loads).
* **Model Evaluation Metrics:** Developed proficiency in utilizing key evaluation metrics including Root Mean Squared Error (RMSE), R-squared (R²), and Mean Absolute Error (MAE) to rigorously assess model accuracy, generalization, and fit to energy consumption data.
* **Cross-Validation & Hyperparameter Tuning:** Understood and implemented robust validation techniques like k-fold cross-validation to ensure model reliability and prevent overfitting. Gained initial experience with hyperparameter tuning to optimize model performance.
* **Feature Engineering and Selection:** Explored methods for transforming raw simulation and climate datasets into effective features for ML models, including techniques for data cleaning, handling missing values, and selecting the most impactful variables for energy prediction.
* **Data Pipelines and Cleaning:** Established foundational data processing pipelines to efficiently prepare real-world simulation and climate datasets for machine learning training, ensuring data quality and consistency.
* **Tools:** Gained hands-on proficiency with `scikit-learn` for implementing various supervised learning algorithms and `Jupyter notebooks` for interactive data analysis, model development, and visualization. Began exploring `PyTorch` for basic neural network concepts.

## 🧪 Key Mini-Projects & Exercises

* **Annual Heating Load Predictor:** Developed and trained machine learning models to predict annual heating loads using a dataset of building parameters (e.g., area, U-values, window-to-wall ratio) and climate data. This project demonstrated the ability to build energy-specific predictive models.
    * [Link to `train_model.py` in `mini_projects/03_train_ml_models_energy_performance/`](../mini_projects/03_train_ml_models_energy_performance/train_model.py) *(Adjust path as needed)*
* **ML Model Comparison for Energy Use Prediction:** Implemented and systematically compared the performance of different supervised ML models (e.g., Linear Regression vs. Random Forest) for predicting building energy use, analyzing their strengths, weaknesses, and suitability for various energy prediction tasks.
    * [Link to relevant notebook/script, e.g., `notebooks/01_ml_model_comparison.ipynb`](../notebooks/01_ml_model_comparison.ipynb) *(Adjust path as needed)*
* **Cross-Validation and Hyperparameter Tuning Experiment:** Applied cross-validation techniques to ensure model robustness and performed initial hyperparameter tuning (e.g., for Random Forests) to optimize predictive accuracy for energy consumption.
    * [Link to relevant notebook/script, e.g., `notebooks/02_model_tuning_validation.ipynb`](../notebooks/02_model_tuning_validation.ipynb) *(Adjust path as needed)*
* **Evaluation Metrics Visualization:** Created informative visualizations (e.g., scatter plots of predicted vs. actual values, residual plots, error distributions) to effectively communicate model performance, identify biases, and highlight areas for improvement.
    * [Link to a relevant visualization script or notebook, e.g., `mini_projects/02_visualize_energyplus_csv_outputs/viz_script.py` or a new dedicated ML visualization notebook](your_github_link_to_file) *(If you create a specific one for ML results)*
* **Simple Neural Network in PyTorch:** Implemented a basic feedforward neural network in PyTorch for a regression task (e.g., a simplified energy prediction), gaining foundational experience with deep learning frameworks.
    * [Link to relevant notebook/script, e.g., `notebooks/03_pytorch_intro_nn.ipynb`](../notebooks/03_pytorch_intro_nn.ipynb) *(Adjust path as needed)*

## 📚 Key Readings & Resources

* *Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow*, Aurélien Géron – Chapters on regression, model evaluation, and basic neural networks.
* *Introduction to Machine Learning with Python*, Andreas C. Müller & Sarah Guido – Chapters on supervised learning, model evaluation, and feature engineering.
* Scikit-learn User Guide ([scikit-learn.org/stable/user_guide.html](https://scikit-learn.org/stable/user_guide.html)) – Official documentation for in-depth understanding of algorithms and tools.
* PyTorch Official Tutorials ([pytorch.org/tutorials](https://pytorch.org/tutorials)) – Guided introductions to building and training neural networks.
* Relevant academic papers on Machine Learning for building energy prediction and surrogate modeling in architectural design.

## 📚 Detailed Learning & Documentation

For a comprehensive breakdown of concepts, code examples, and my daily reflections during this phase, please refer to:

* [**Phase 2 Progress Log**](01_progress_log.md) 
* [**Notes on Scikit-learn Basics**](02_notes_sklearn_basics.md)
* [**Notes on PyTorch Introduction**](03_notes_pytorch_intro.md)
* [**Notes on Dataset Preparation**](04_dataset_preperation.md)

## ➡️ Moving Forward

Building upon these predictive capabilities and model evaluation skills, the next phase will integrate these ML models directly into **Generative Design workflows**. This will enable the exploration and optimization of architectural layouts, informed by real-time energy performance feedback provided by the trained surrogate models.