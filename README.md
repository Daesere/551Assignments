# Capitol Bike Share Linear Regression Analysis

## Overview
This project implements a linear regression model to predict bike rental counts from the Capitol Bike Share dataset using environmental and temporal features. The analysis includes data preprocessing, feature engineering, and model evaluation.

## Prerequisites
- Google account (to access Google Colab)
- `day.csv` dataset file from the [UCI Bike Sharing Dataset](https://archive.ics.uci.edu/ml/datasets/bike+sharing+dataset)

## How to Run

### Step 1: Open in Google Colab
1. Upload the `551A1.ipynb` file to Google Colab, or
2. Open Google Colab and select `File > Upload notebook` and choose the notebook file

### Step 2: Upload the Dataset
When you run the first code cell (Section 1.1), you will see a file upload prompt:
1. Click the **"Choose Files"** button
2. Select the `day.csv` file from your local machine
3. Wait for the upload to complete (you'll see "Saving day.csv to day.csv" when done)

The file upload cell looks like this:
```python
from google.colab import files
uploaded = files.upload()
```

### Step 3: Run All Cells
After uploading the dataset:
1. Click `Runtime > Run all` from the menu, or
2. Run cells sequentially using `Shift + Enter`

## What the Code Does

### Task 1: Data Preprocessing and Exploration
- Loads and cleans the dataset
- Performs one-hot encoding for categorical features
- Generates visualization plots including:
  - Scatter plots of environmental variables vs. rental count
  - Temperature vs. count with quadratic fit
  - Temperature-humidity interaction heatmap
  - Monthly seasonal pattern

### Task 2: Linear Regression Implementation
- Implements linear regression using the closed-form solution
- Applies feature engineering techniques:
  - **Polynomial features**: Squared terms for temp, atemp, humidity, windspeed
  - **Interaction terms**: Combined effects between environmental variables
  - **Log transformations**: Applied to humidity and windspeed
  - **Sine/cosine encoding**: Cyclical encoding for month and weekday
- Evaluates model performance across different feature engineering stages
- Compares results between raw and one-hot encoded data

## Expected Outputs
- Data visualization plots (8 subplots + 3 feature engineering plots)
- MSE comparison table showing Train MSE, Test MSE, and Gap(%) for each feature engineering stage
- Line plot showing model evolution across complexity stages

## Key Results
The analysis shows that feature engineering significantly improves model performance, with polynomial features providing the largest reduction in MSE. Sine/cosine encodings for temporal features and interaction terms provide moderate improvements.

## Notes
- The code runs approximately 100 iterations with different random seeds for robust evaluation
- Total runtime is approximately 2-5 minutes depending on Colab resources
- All required Python packages (pandas, numpy, matplotlib, seaborn, sklearn) are pre-installed in Google Colab