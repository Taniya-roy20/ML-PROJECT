# ML-PROJECT


## 📌 Project Overview

This project focuses on predicting apple yield using historical agricultural data and different regression techniques.

The project compares three machine learning approaches:

1. **Linear Regression**
2. **Polynomial Regression**
3. **Multivariate Linear Regression**

The models are evaluated using four standard regression metrics:

* Mean Squared Error (MSE)
* Root Mean Squared Error (RMSE)
* Mean Absolute Error (MAE)
* R² Score

The main objective is to determine which regression model performs best for predicting apple yield based on historical data.

---

## 🎯 Objectives

The objectives of this project are:

* Analyze historical apple production data.
* Study the relationship between year and apple yield.
* Build a Linear Regression model.
* Build a Polynomial Regression model.
* Build a Multivariate Linear Regression model.
* Evaluate the models using MSE, RMSE, MAE and R².
* Compare the performance of all models.
* Identify the best-performing regression model.
* Predict future apple yield using the selected model.

---

## 📊 Dataset

The dataset used in this project is based on historical FAOSTAT agricultural data.

The dataset contains information related to apple production, including:

* Year
* Area harvested
* Yield
* Element
* Value

The original dataset stores **Area Harvested** and **Yield** as separate observations for each year. Therefore, the data is preprocessed and reshaped so that each year contains both area harvested and yield values.

### Processed Dataset Structure

| Feature        | Description                     |
| -------------- | ------------------------------- |
| Year           | Year of observation             |
| Area_Harvested | Area used for apple cultivation |
| Yield          | Apple yield in kg/ha            |

---

## 🔧 Data Preprocessing

The following preprocessing steps are performed:

1. Load the CSV dataset using Pandas.
2. Select the required columns.
3. Convert Year and Value columns to numeric values.
4. Remove missing values.
5. Separate Area Harvested and Yield observations.
6. Rename the columns.
7. Merge the two datasets using Year.
8. Sort the observations chronologically.

The resulting dataset contains one row per year.

---

# 🤖 Machine Learning Models

## 1. Linear Regression

Linear Regression is used to model the relationship between year and apple yield.

The model can be represented as:

**Yield = β₀ + β₁(Year)**

### Input

* Year

### Output

* Yield

This model assumes that the relationship between year and yield is approximately linear.

---

## 2. Polynomial Regression

Polynomial Regression extends Linear Regression by introducing polynomial terms of the input variable.

For a degree-2 polynomial:

**Yield = β₀ + β₁(Year) + β₂(Year²)**

Polynomial Regression is useful when the relationship between year and yield is nonlinear.

In this project, polynomial regression can be tested using different polynomial degrees, with degree 2 used as the initial model.

---

## 3. Multivariate Linear Regression

Multivariate Linear Regression uses more than one independent variable to predict yield.

The model used in this project is:

**Yield = β₀ + β₁(Year) + β₂(Area_Harvested)**

### Input Features

* Year
* Area Harvested

### Target

* Yield

This model allows the prediction to consider both the historical time trend and the area used for apple cultivation.

---

# 📏 Model Evaluation

The models are evaluated using four regression metrics.

## Mean Squared Error (MSE)

MSE measures the average squared difference between actual and predicted values.

**Lower MSE indicates better performance.**

---

## Root Mean Squared Error (RMSE)

RMSE is the square root of MSE.

It represents the prediction error in the same unit as the target variable.

**Lower RMSE indicates better performance.**

---

## Mean Absolute Error (MAE)

MAE measures the average absolute difference between actual and predicted values.

**Lower MAE indicates better performance.**

---

## R² Score

R² measures how much of the variation in the target variable is explained by the model.

**Higher R² indicates better performance.**

An R² value closer to 1 indicates a stronger model fit.

---

# 🧪 Train-Test Strategy

Because the dataset represents observations across different years, a chronological train-test split is used instead of a random split.

### Training Data

Historical observations up to 2014.

### Testing Data

Observations after 2014.

This approach helps evaluate how well the models can predict later observations using earlier historical information.

---

# 📈 Model Comparison

The three models are compared using:

| Model                          | MSE | RMSE | MAE | R² |
| ------------------------------ | --: | ---: | --: | -: |
| Linear Regression              |   — |    — |   — |  — |
| Polynomial Regression          |   — |    — |   — |  — |
| Multivariate Linear Regression |   — |    — |   — |  — |

The actual values are generated automatically when the model comparison script is executed.

### Best Model

The best model is selected based on:

* Lowest MSE
* Lowest RMSE
* Lowest MAE
* Highest R²

The project also calculates an overall ranking based on all four metrics.

---

# 📊 Results and Visualizations

The project generates several visualizations:

### 1. MSE Comparison

Compares the Mean Squared Error of all models.

### 2. RMSE Comparison

Compares the Root Mean Squared Error of all models.

### 3. MAE Comparison

Compares the Mean Absolute Error of all models.

### 4. R² Comparison

Compares the R² Score of all models.

### 5. Actual vs Predicted Yield

Shows the actual yield and predictions produced by each model for the test period.

---

# 🔮 Future Prediction

The multivariate model requires both:

* Year
* Area Harvested

for future prediction.

Since future area harvested values are not available in the historical dataset, a separate trend-based regression is used to estimate area harvested for future years.

The estimated area harvested is then supplied to the multivariate model to generate future yield predictions.

The project can be used to generate predictions for:

* 2027
* 2028
* 2029
* 2030

These predictions should be interpreted as model-based estimates rather than guaranteed future values.

---

# 🛠️ Technologies Used

* Python
* NumPy
* Pandas
* Matplotlib
* Scikit-learn
* Jupyter Notebook / Google Colab

---

# 📂 Project Structure

```text
apple-yield-prediction-ml/
│
├── data/
│   └── apple.csv
│
├── src/
│   ├── linear_regression.py
│   ├── polynomial_regression.py
│   ├── multivariate_regression.py
│   └── model_comparison.py
│
├── results/
│   ├── model_comparison.csv
│   ├── prediction_comparison.csv
│   ├── model_comparison_mse.png
│   ├── model_comparison_rmse.png
│   ├── model_comparison_mae.png
│   ├── model_comparison_r2.png
│   └── all_models_prediction_comparison.png
│
├── Apple_Yield_Prediction.ipynb
├── requirements.txt
├── README.md
└── .gitignore
```

---

---

