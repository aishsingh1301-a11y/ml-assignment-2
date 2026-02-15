# ml-assignment-2
BITS M.Tech ML Assignment 2

# Machine Learning Assignment 2 - Breast Cancer Classification

## a. Problem statement
The task is to build classification models to predict whether a breast tumor is **malignant** (0) or **benign** (1) based on features extracted from digitized images of fine needle aspirates of breast masses.  
We implement and compare six classification algorithms and deploy an interactive Streamlit application to demonstrate model predictions and performance metrics.

## b. Dataset description
- **Name**: Breast Cancer Wisconsin (Diagnostic)  
- **Source**: Built-in scikit-learn dataset (originally from UCI Machine Learning Repository)  
- **Instances**: 569  
- **Features**: 30 real-valued features (mean, standard error, and worst values of cell nucleus characteristics such as radius, texture, perimeter, area, smoothness, compactness, concavity, concave points, symmetry, fractal dimension)  
- **Target**: Binary classification (0 = malignant, 1 = benign)  
- **Reference**: https://archive.ics.uci.edu/dataset/17/breast+cancer+wisconsin+diagnostic  
- All features are numeric → no categorical encoding required. Data is scaled using StandardScaler before training.

## c. Models used

Comparison Table with evaluation metrics (calculated on test set, 20% split):

=== Model Comparison Table ===

<img width="828" height="194" alt="image" src="https://github.com/user-attachments/assets/d84c1422-f904-4d47-a2bc-5db350395282" />

### Observations on the performance of each model on the chosen dataset

| ML Model Name            | Observation about model performance                                                                 |
|--------------------------|------------------------------------------------------------------------------------------------------|
| Logistic Regression      | Excellent linear model performance. Very high AUC and balanced precision/recall. Highly interpretable and reliable baseline. |
| Decision Tree            | Good recall but slightly lower precision due to overfitting tendency. Simple and explainable but outperformed by ensembles. |
| kNN                      | Performs very well after feature scaling. High recall (catches almost all malignant cases). Distance-based method suits this dataset. |
| Naive Bayes              | Surprisingly strong despite independence assumption. Very high recall, fast training — good for quick prototyping. |
| Random Forest (Ensemble) | Strong ensemble — reduces variance, excellent AUC, robust to noise. Slightly better than single tree in all metrics. |
| XGBoost (Ensemble)       | Best overall performer. Highest AUC and MCC. Excellent handling of feature interactions and class imbalance via boosting. |

The dataset is relatively clean and well-separated, which is why most models achieve >95% accuracy. Ensemble methods (Random Forest & XGBoost) consistently provide the best generalization.

## Deployment
- Streamlit App: Deployed on Streamlit Community Cloud  
- Repository: https://github.com/aishsingh1301-a11y/ml-assignment-2
- Live App:
