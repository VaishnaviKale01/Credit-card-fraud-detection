# Credit-card-fraud-detection
Fraud detection with imbalanced data, threshold tuning, and model trade-offs.
## Problem Statement
The goal of this project is to detect fraudulent in an extremely imbalanced dataset.
## Dataset
- Source: Kaggle Credit Card Fraud Dataset
- Rows : ~284,000
- Features : 30 numerical features + target
- Fraud Rate : 0.17%
All features are anonymized PCA components, except Time and Amount
## Project Structure
credit-card-fraud-detection
    data/ 
        creditcard.csv
    notebooks/
        01_data_understanding.ipynb
        02_logistic_regression.ipynb
        03_threshold_tuning.ipynb
        04_random_forest_exploration.ipynb
    README.md
    requirements.txt
Each notebook is self-contained and can be run independently from raw data.
## Modeling Approach
### Logistic Regression (Baseline)
- Used as a strong, interpretable baseline
- Handled class imbalance using class weights
- Performed feature selection and retraining
- Evaluted using ROC-AUC, Recall, precision and confusion matrices
### Random Forest Exploration
Random Forest models were explored to evaluate whether non-linear relarionships could improve performance.
Due to dataset size and hardware constraints (8GB RAM), extensive cross-validated hyperparameter tuning was computationally expensive
and offered limited performance gains over logistic regression.
### Final Model Choice
Given performance, interpretability, and computational efficiency, weighted logistic regression with threshold tuning was selected as the final model for this project.
## Future Work
With additional computational resources, gradient boosting methods (e.g. XGBoost or LightGBM) with early stopping could be explored to further improve performance.
## Requirements
- Python 3.x
- scikit-learn
- numpy
- matplotlib/seaborn
- imbalanced-learn
