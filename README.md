# 🏠 House Prices — Advanced Regression Techniques

A complete machine learning regression project based on the **House Prices: Advanced Regression Techniques** Kaggle competition.

The objective is to predict the final sale price of residential properties in **Ames, Iowa**, using 79 explanatory variables describing different aspects of each property.

The project covers the complete machine learning workflow, including data quality checks, preprocessing, baseline modeling, hyperparameter tuning, and model retraining.

---

## 🎯 Project Objective

Using **79 explanatory variables** describing almost every aspect of residential homes in Ames, Iowa, the goal is to predict the final **SalePrice** of each house.

The project focuses on applying and comparing multiple regression algorithms while building a structured preprocessing and modeling pipeline.

The original Kaggle competition evaluates submissions using **Root Mean Squared Error (RMSE)** between the logarithm of the predicted sale price and the logarithm of the observed sale price.

The required submission format contains:

```text
Id
SalePrice
```

---

## 📊 Dataset

The dataset is provided by the Kaggle competition:

[House Prices: Advanced Regression Techniques — Kaggle](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques?utm_source=chatgpt.com)

### Dataset Overview

* **Location:** Ames, Iowa
* **Problem Type:** Regression
* **Target Variable:** `SalePrice`
* **Number of Explanatory Variables:** 79
* **Target:** Final residential sale price

The features describe many aspects of residential properties, including size, quality, condition, construction characteristics, and other house attributes.

---

# 🔬 Project Workflow

```text
Raw Data
    │
    ▼
Data Quality Checks
    │
    ├── Missing Values
    ├── Duplicate Records
    ├── Data Types
    └── Feature Inspection
    │
    ▼
Data Preprocessing
    │
    ├── Numerical Features
    └── Categorical Features
    │
    ▼
ColumnTransformer
    │
    ▼
Baseline Models
    │
    ├── Linear Regression
    ├── Lasso
    ├── Ridge
    ├── KNN
    ├── Decision Tree
    ├── Random Forest
    └── XGBoost
    │
    ▼
Model Evaluation
    │
    ▼
Hyperparameter Tuning
    │
    ├── Random Forest
    └── KNN
    │
    ▼
Retraining
    │
    ▼
Final Evaluation
    │
    ▼
Kaggle Submission
```

---

# 1️⃣ Data Quality Checks

The first stage focuses on understanding the structure and quality of the dataset before applying machine learning algorithms.

The following checks are performed:

* Missing-value analysis
* Duplicate-record detection
* Data type inspection
* Numerical feature inspection
* Categorical feature inspection
* Target-variable inspection
* General dataset structure analysis

These checks help identify potential issues that need to be addressed during preprocessing.

---

# 2️⃣ Data Preprocessing

The dataset contains both numerical and categorical variables, so different preprocessing strategies are required.

A **ColumnTransformer** is used to apply the appropriate transformations to each feature type.

### Numerical Features

Numerical variables are processed through the numerical preprocessing pipeline.

### Categorical Features

Categorical variables are processed separately to transform them into a machine-learning-compatible representation.

### Preprocessing Structure

```text
                 Input Dataset
                       │
          ┌────────────┴────────────┐
          │                         │
   Numerical Features       Categorical Features
          │                         │
          ▼                         ▼
 Numerical Pipeline       Categorical Pipeline
          │                         │
          └────────────┬────────────┘
                       ▼
                ColumnTransformer
                       │
                       ▼
              Final Feature Matrix
```

This approach provides a consistent preprocessing workflow that can be reused during training and prediction.

---

# 3️⃣ Baseline Models

Several regression algorithms are trained as baseline models to establish an initial performance benchmark.

The models include:

* Linear Regression
* Lasso Regression
* Ridge Regression
* K-Neighbors Regressor
* Random Forest Regressor


---

## 📊 Baseline Model Performance

The following results were obtained on the **training set**.

| Model                   |   RMSE |    MAE |     R² |
| ----------------------- | -----: | -----: | -----: |
| Linear Regression       | 0.0000 | 0.0000 | 1.0000 |
| Lasso                   | 0.0404 | 0.0229 | 1.0000 |
| Ridge                   | 0.0000 | 0.0000 | 1.0000 |
| K-Neighbors Regressor   |      — |      — | 1.0000 |
  

### Baseline Evaluation Metrics

The following metrics are used during model evaluation:

* **MAE — Mean Absolute Error**
* **MSE — Mean Squared Error**
* **RMSE — Root Mean Squared Error**
* **R² — R-squared**

---

# 4️⃣ Hyperparameter Tuning

After establishing the baseline models, hyperparameter tuning is performed for selected algorithms.

The tuning stage focuses on:

* Random Forest Regressor
* K-Neighbors Regressor

The objective is to investigate whether optimized hyperparameters can improve model performance compared with the initial configurations.

---

## 🌲 Random Forest — Tuned Model

The tuned Random Forest model achieved the following training performance:

```text
Root Mean Squared Error: 2224.3074
Mean Absolute Error:      241.2821
R² Score:                    0.9992
```

---

## 👥 K-Neighbors — Tuned Model

The tuned K-Neighbors model achieved:

```text
Root Mean Squared Error: 6299.3877
Mean Absolute Error:     883.9607
R² Score:                   0.9937
```

---

## ⚙️ Hyperparameter Tuning Results

| Model                   |      RMSE |      MAE |     R² |
| ----------------------- | --------: | -------: | -----: |
| Random Forest Regressor | 2224.3074 | 241.2821 | 0.9992 |
| K-Neighbors Regressor   | 6299.3877 | 883.9607 | 0.9937 |

### Tuning Progress

```text
Baseline Models
      │
      ▼
Initial Model Evaluation
      │
      ▼
Hyperparameter Tuning
      │
      ├───────────────┐
      ▼               ▼
Random Forest        KNN
      │               │
      └───────┬───────┘
              ▼
        Tuned Models
```

---

# 5️⃣ Model Retraining

Following model development and hyperparameter tuning, the models can be retrained using the prepared dataset.

This stage allows the selected model configurations to be retrained on the prepared data before generating final predictions.


---

# 7️⃣ Kaggle Submission

The final prediction file must contain:

```text
Id,SalePrice
```

The prediction workflow is:

```text
Test Dataset
     │
     ▼
Same Preprocessing Pipeline
     │
     ▼
Trained Model
     │
     ▼
SalePrice Predictions
     │
     ▼
Submission File
     │
     ├── Id
     └── SalePrice
```

The submission can then be uploaded to the Kaggle competition for evaluation.

---

# 🛠️ Technologies & Libraries

### Programming

* Python

### Data Analysis

* Pandas
* NumPy

### Visualization

* Matplotlib
* Seaborn

### Machine Learning

* Scikit-learn
* XGBoost

### Development Tools

* Jupyter Notebook
* VS Code
* Git
* GitHub


---

# 🚀 Future Improvements

The next stages of the project can include:

* Applying `log1p` transformation to `SalePrice`
* Using K-Fold cross-validation
* Building a dedicated validation set
* Performing advanced feature engineering
* Investigating skewed numerical variables
* Feature selection
* XGBoost hyperparameter tuning
* Comparing additional boosting algorithms
* Evaluating models using the Kaggle RMSE formulation
* Generating the final Kaggle submission
* Comparing local validation results with Kaggle performance

---

# 📚 Data Source

[House Prices: Advanced Regression Techniques — Kaggle](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques?utm_source=chatgpt.com)

---

## 👩‍💻 Project Summary

This project implements an end-to-end machine learning workflow for residential house price prediction, covering **data quality checks, preprocessing, baseline regression models, hyperparameter tuning, and model retraining**.

The project provides a practical comparison of different regression approaches and establishes a foundation for further improvements through feature engineering, cross-validation, and Kaggle-oriented evaluation.
