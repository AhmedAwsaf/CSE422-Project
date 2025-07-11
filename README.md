# Stroke Prediction Using Machine Learning - 2023

## Table of Contents
1. [Introduction](#introduction)
2. [Collaborators](#collaborators)
3. [Dataset Description](#dataset-description)
4. [Dataset Pre-processing](#dataset-pre-processing)
5. [Feature Scaling](#feature-scaling)
6. [Dataset Splitting](#dataset-splitting)
7. [Model Training and Testing](#model-training-and-testing)
8. [Model Selection/Comparison Analysis](#model-selectioncomparison-analysis)
9. [Conclusion](#conclusion)

## Introduction
This project represents a machine-learning process designed to predict the probability of a stroke among different patients. The dataset used for this prediction is derived from various medical reports. Early detection and prevention of strokes are crucial in healthcare, and this model facilitates the early identification of potential stroke patients.

## Collaborators
<div align="center">

| Contributor        | GitHub Profile                                                                                 | Followers                                                                                           |
|--------------------|------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------|
| **Ahmed Awsaf**    | [![Ahmed's GitHub](https://img.shields.io/badge/-AhmedAwsaf-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/AhmedAwsaf) | ![Followers](https://img.shields.io/github/followers/AhmedAwsaf?label=Follow&style=social)          |
| **Zaima Mashiat**  | [![Zaima's GitHub](https://img.shields.io/badge/-zaimamashiat-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/zaimamashiat) | ![Followers](https://img.shields.io/github/followers/zaimamashiat?label=Follow&style=social)       |
</div>

## Dataset Description

- **Source**: [Stroke Prediction Dataset on Kaggle](https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset)  
- **Features**:
  - **ID**: A unique identifier for each patient.
  - **Gender**: Male or Female.
  - **Age**: The age of the patient.
  - **Hypertension**: 1 if the patient has hypertension, 0 otherwise.
  - **Heart_disease**: 1 if the patient has heart disease, 0 otherwise.
  - **Ever_married**: "Yes" or "No".
  - **Work_type**: Categorical values like Children, Govt_job, Never_worked, Private, Self_Employed.
  - **Residence_type**: Rural or Urban.
  - **Avg_glucose_level**: The average glucose level in the body.
  - **BMI**: Body Mass Index.
  - **Smoking_status**: Formerly smoked, Never smoked, Smokes, Unknown.
  - **Stroke**: 1 if the patient had a stroke, 0 otherwise.

- **Problem Type**: This is a **classification problem** as the goal is to predict whether or not a patient will have a stroke based on the input features.
- **Data Points**: 5,110 data points.

### Feature Type
- **Quantitative Features**: ID, Age, Avg_glucose_level, BMI
- **Categorical Features**: Gender, Hypertension, Heart_disease, Ever_married, Work_type, Residence_type, Smoking_status, Stroke

## Dataset Pre-processing

### Issues:
- Null values in the BMI attribute.
- Unnecessary "ID" column.
- Categorical features like `gender` and `ever_married` that need encoding.
- The "Residence_type_Rural" and "Residence_type_Urban" columns had low correlation.

### Solutions:
- **Deleting Columns**: The "ID" column was removed as it was irrelevant.
- **Handling Missing Values**: Null values in BMI were replaced with the mean value.
- **Encoding**: Categorical values in `gender`, `ever_married`, and `work_type` were encoded into numeric values.

## Feature Scaling

- **Before Pre-processing**: Scatter plot showing raw data.
- **After Pre-processing**: Standard scaling was applied to `Avg_glucose_level` and `BMI` to normalize the data range between 0 and 10.

## Dataset Splitting

- **Train Set**: 80% of the dataset (4,088 data points).
- **Test Set**: 20% of the dataset (1,022 data points).

## Model Training and Testing

We used the following models for classification:

1. **K-Nearest Neighbors (KNN)**: 
   - Non-parametric.
   - Majority voting based on K nearest neighbors.
   - K = 5 by default.

2. **Random Forest**:
   - Decision trees built from random parts of the dataset.
   - Voting from multiple decision trees for the final prediction.

3. **Logistic Regression**:
   - Statistical regression for classification.
   - Suitable for simpler classification problems.

## Model Selection/Comparison Analysis

The models provided nearly identical accuracy (around 95%). However:
- **Logistic Regression** showed high precision.
- **KNN** excelled in recall and F1 scores.

## Conclusion

The project successfully predicted stroke probabilities with an average accuracy of 95%. However, the model performance could be improved by addressing dataset imbalances, tuning model parameters (e.g., K in KNN), and employing SMOTE for data augmentation.

Future work involves further model refinement and real-world testing for improved stroke prediction accuracy.
