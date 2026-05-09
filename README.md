# Heart Disease Prediction (AI/ML Project)

## Dataset
- Hear Disease Dataset (1,025 entries)

## Phases
- Phase 1: Data Collection
- Phase 2: EDA & Data Processing
- Phase 3: Data Training & Integration

## Project Overview
The Heart Disease Prediction Project is an end-to-end machine learning system designed to predict the presence of cardiovascular disease in patients based on clinical health metrics. By leveraging a structured data pipeline, the project encompasses data cleaning, feature engineering, and the training of multiple classification models-including Logistic Regression, K-Nearest Neighbors (KNN), and Support Vector Machines (SVM)-to provide accurate health risk assessments.

# Phase 1: Data Collection
Data Source: [Kaggle]

Dataset Size: 1,025 rows, 14 features.

# Phase 2: EDA & Processing
Cleaning:
- Removed id
- Converted age to years
- Handled nulls using median imputation

Key Insights: 
- Cleaning: The dataset was prepared by removing the irrelevant id column, scaling the age feature to years for better interpretability, and applying median imputation to ensure data completeness.

- Heatmap Insights: The correlation heatmap demonstrates that age, cholesterol, and weight exhibit the strongest positive correlations with the presence of cardiovascular disease, while other features show weaker individual linear relationships. The data distribution is well-balanced across the target classes, providing a reliable basis for model training.

# Phase 3: Training & Integration
Models Used:
- Logistic Regression
- KNN
- SVM.

Best Performing Model: 
- Support Vector Machine (SVM)  
- Final Accuracy: ~88.78%
- Why?:
    - 1. Non-Linear Decision Boundaries:Logistic Regression failed to capture the complexity of the clinical metrics. SVM with an RBF (Radial Basis Function) Kernel     successfully mapped the health data into higher dimensions to find a more accurate boundary between "Risk" and "No Risk."
    - 2. Hyperparameter Optimization:We used `GridSearchCV` to mathematically determine that `C=1` and `gamma=0.1` provided the best balance, preventing the model from overfitting while maintaining high predictive power.
    - 3. Clinical Scalability:By utilizing `StandardScaler`, we ensured that high-value features like Cholesterol (200+) didn't numerically overwhelm features like Sex or FBS (0/1), allowing the model to treat all health indicators with appropriate weight.

How to Run
- Set up a virtual environment: python -m venv myenv

- Install requirements: pip install -r requirements.txt

- Execute notebooks in order (Phase 1 -> Phase 2 -> Phase 3).
