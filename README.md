
#  Wine Quality Prediction

This project aims to predict the quality of red wines from the Portuguese "Vinho Verde" dataset using machine learning techniques. The dataset consists of physicochemical (input) and sensory (output) variables. The goal is to classify wines as **good quality** or **bad quality** based on these attributes.

---

## Table of Contents
- [Dataset Information](#dataset-information)  
- [Features](#features)  
- [Target Variable](#target-variable)  
- [Project Workflow](#project-workflow)  
- [Exploratory Data Analysis](#exploratory-data-analysis)  
- [Model Training and Evaluation](#model-training-and-evaluation)  
- [Results](#results)  
- [Conclusion](#conclusion)  
  

---

## Dataset Information

- Number of entries: 6,497  
- Data type: Numeric and categorical  
- Task type: Classification (Good vs Bad quality)  

---

## Features

| Feature                  | Description |
|---------------------------|-------------|
| `fixed_acidity`           | Fixed acidity of the wine |
| `volatile_acidity`        | Volatile acidity of the wine |
| `citric_acid`             | Citric acid content |
| `residual_sugar`          | Amount of residual sugar |
| `chlorides`               | Salt content |
| `free_sulfur_dioxide`     | Free SO₂ concentration |
| `total_sulfur_dioxide`    | Total SO₂ concentration |
| `density`                 | Wine density |
| `pH`                      | Wine pH |
| `sulphates`               | Sulphate content |
| `alcohol`                 | Alcohol percentage |

---

## Target Variable

- `good-quality`:  
  - 1 → Good quality (quality score ≥ 7)  
  - 0 → Bad quality (quality score < 7)

---

## Project Workflow

1. **Data Loading**  
   Loaded the dataset using `pandas`.

2. **Data Preprocessing**  
   - Checked for missing values  
   - Dropped irrelevant categorical columns (`color`)  
   - Scaled features using `StandardScaler`  
   - Applied SMOTE for class imbalance handling

3. **Exploratory Data Analysis (EDA)**  
   - Visualized distributions of good vs bad wines  
   - Checked correlation between features  
   - Scatter plots for important feature pairs  

4. **Train-Test Split**  
   - Split dataset into training and testing sets (70:30 ratio)

5. **Model Training**  
   Trained the following classifiers:  
   - Random Forest  
   - Decision Tree  
   - K-Nearest Neighbors (KNN)  
   - Support Vector Machine (SVM)  
   - Logistic Regression

6. **Model Evaluation**  
   - Accuracy  
   - F1-score  
   - Confusion Matrix  
   - MAE & RMSE

---

## Exploratory Data Analysis

- Count of good vs bad quality wines:
  
  ![Good vs Bad Wines](images/good_bad_count.png)

- Correlation heatmap of features:
  
  ![Correlation Heatmap](images/correlation_heatmap.png)

- Scatter plots for feature interactions:
  
  ![Scatter Plots](images/scatter_plots.png)

---

## Model Training and Evaluation

| Model                     | Accuracy | F1-Score | MAE   | RMSE  |
|----------------------------|----------|----------|-------|-------|
| Random Forest              | 0.88     | 0.64     | 0.116 | 0.340 |
| Decision Tree              | 0.83     | 0.49     | 0.168 | 0.410 |
| K-Nearest Neighbors        | 0.80     | 0.39     | 0.196 | 0.443 |
| Support Vector Machine     | 0.81     | 0.00     | 0.187 | 0.433 |
| Logistic Regression        | 0.81     | 0.28     | 0.186 | 0.431 |



---

## Results

- Random Forest outperformed other models with an accuracy of **88.15%**.  
- KNN and Decision Tree performed moderately well, while SVM and Logistic Regression showed lower performance due to imbalanced data and model limitations.  
- Feature importance from Random Forest indicates **alcohol, volatile acidity, and sulphates** are the most influential features in predicting wine quality.

---

## Conclusion

The Random Forest model is the best performing model for predicting red wine quality in this dataset. With appropriate feature scaling and handling class imbalance using SMOTE, the model can successfully classify good and bad quality wines with high accuracy.

---












