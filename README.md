# HIV/AIDS Survival Outcome Prediction Using Machine Learning

## Project Overview

This project explores the application of supervised machine learning techniques to predict clinical outcomes using data from the ACTG 175 HIV clinical trial.

The primary objective is to investigate whether baseline clinical and demographic characteristics can help distinguish between patients with recorded treatment failure and those whose outcomes were censored.

The project focuses on classification model development, exploratory data analysis, feature selection, class imbalance, hyperparameter optimization, cross-validation, and model evaluation.

## Dataset

- **Dataset:** ACTG 175 HIV Clinical Trial
- **Number of samples:** 2,139
- **Number of features:** 24
- **Problem type:** Binary classification

The dataset contains clinical, demographic, treatment-related, and laboratory measurements.

Some of the variables include:

- Age and weight
- Gender and race
- Treatment information
- Hemoglobin measurements
- CD4 and CD8 cell counts
- Clinical symptoms
- Treatment history

### Target Variable

The analysis uses the recorded outcome label:

- `1` – Treatment failure
- `0` – Censored observation

The target represents a recorded failure-versus-censoring classification label.

## Project Objectives

1. Explore clinical and demographic characteristics associated with recorded clinical outcomes.
2. Perform exploratory data analysis and feature profiling.
3. Prepare clinical variables for supervised machine learning.
4. Investigate the impact of class imbalance on model performance.
5. Develop and compare classification models.
6. Evaluate model performance using multiple classification metrics.
7. Investigate the predictive contribution of baseline clinical features.

## Project Workflow

The overall workflow consists of the following stages:

1. Data loading and inspection
2. Exploratory data analysis
3. Data preprocessing and encoding
4. Feature selection and preparation
5. Target distribution analysis
6. Supervised classification
7. Model evaluation
8. Hyperparameter optimization and cross-validation
9. Performance comparison and interpretation

## Data Preprocessing

The preprocessing workflow involves preparing clinical and demographic variables for machine learning.

Key considerations include:

- Inspecting feature distributions and data types
- Handling categorical variables
- Encoding categorical features
- Scaling numerical features where appropriate
- Examining target class distribution
- Selecting features relevant to baseline prediction

For baseline prediction, variables collected during follow-up must be excluded because they would not be available at the beginning of the trial.

In particular, week-20 measurements such as `CD420` and `CD820` are not considered baseline predictors.

## Machine Learning Models

The primary supervised classification algorithms explored in this project are:

### Random Forest Classifier

An ensemble learning algorithm that combines multiple decision trees to generate classification predictions.

### Logistic Regression

A linear classification algorithm used to estimate the probability of belonging to a particular outcome class.

Additional machine learning techniques explored include:

- Feature selection
- Class balancing
- Hyperparameter optimization using GridSearchCV
- Cross-validation
- Classification threshold evaluation
- ROC curve and ROC-AUC analysis

## Model Evaluation — Baseline Models

Two classification algorithms were evaluated using baseline clinical and demographic features.

### 1. Random Forest — Base Model

| Metric | Score |
|---|---:|
| Accuracy | 0.7617 |
| Precision | 0.5556 |
| Recall | 0.0962 |
| Specificity | 0.9753 |
| F1-score | 0.1639 |
| ROC-AUC | 0.6594 |

**Confusion Matrix**

| | Predicted Negative | Predicted Positive |
|---|---:|---:|
| Actual Negative | 316 | 8 |
| Actual Positive | 94 | 10 |

### 2. Logistic Regression

| Metric | Score |
|---|---:|
| Accuracy | 0.6986 |
| Precision | 0.4277 |
| Recall | 0.7115 |
| Specificity | 0.6944 |
| F1-score | 0.5343 |
| ROC-AUC | 0.7511 |

**Confusion Matrix**

| | Predicted Negative | Predicted Positive |
|---|---:|---:|
| Actual Negative | 225 | 99 |
| Actual Positive | 30 | 74 |

### Comparative Analysis

**Random Forest**

- Achieved an accuracy of approximately 76.2%.
- Demonstrated high specificity (97.53%).
- Had very low recall (9.62%), indicating that it missed most positive cases.
- Achieved a ROC-AUC of 0.6594.

**Logistic Regression**

- Achieved an accuracy of approximately 69.9%.
- Demonstrated substantially higher recall (71.15%).
- Achieved a higher F1-score (0.5343).
- Achieved a higher ROC-AUC (0.7511).

**Overall Interpretation**

Although Random Forest achieved higher accuracy and specificity, Logistic Regression demonstrated better recall, F1-score, and ROC-AUC.

Therefore, Logistic Regression provided a more balanced baseline classification performance, particularly when identifying positive cases was important.

## Conclusion

This project demonstrates the application of supervised machine learning techniques to clinical trial data for investigating recorded clinical outcomes.

The baseline model comparison showed that model performance can vary considerably depending on the classification algorithm and evaluation metric.

Random Forest demonstrated a tendency to predict the negative class, resulting in high specificity but poor recall. Logistic Regression provided a better balance between identifying positive and negative cases.

The results highlight the importance of considering class imbalance, feature availability, model selection, and multiple evaluation metrics when developing predictive models using clinical datasets.

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

## Repository Contents

The repository is intended to contain:

- Jupyter Notebook containing the data analysis and machine learning workflow
- Project documentation
- Model evaluation results
- Supporting visualizations

## Important Considerations

The classification target represents the recorded failure-versus-censoring label. This project is a classification-based exploration and should not be interpreted as a conventional time-to-event survival analysis.

The models are exploratory and are not clinically validated or intended for clinical decision-making.

---

**Author:** Nagendra Prasad
