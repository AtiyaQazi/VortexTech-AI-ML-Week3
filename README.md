# VortexTech AI & ML Internship-Week 3

## Regression and Clustering on Real Data

This project was completed as part of the VortexTech AI & ML Internship-Week 3.

The project demonstrates both supervised and unsupervised machine learning techniques using real-world datasets.

## Project Objectives

* Build a regression model for a continuous numeric target.
* Evaluate the regression model using RMSE and R².
* Apply K-Means clustering to customer data.
* Use the Elbow Method to determine a reasonable number of clusters.
* Visualize customer clusters in 2D.
* Interpret the resulting customer segments.

## Datasets

### 1. California Housing Dataset

File:

`data/housing.csv`

The regression task predicts:

`median_house_value`

The dataset contains housing-related numerical features and the categorical `ocean_proximity` feature.

### 2. Mall Customers Dataset

File:

`data/Mall_Customers.csv`

The clustering analysis uses:

* Age
* Annual Income (k$)
* Spending Score (1-100)

`CustomerID` was excluded because it is an identifier, while `Genre` was excluded because this analysis focuses on numerical customer characteristics.

## Regression

### Preprocessing

* Inspected the dataset.
* Checked missing values and duplicates.
* Filled missing `total_bedrooms` values using the column median.
* Applied one-hot encoding to `ocean_proximity`.
* Split the data into 80% training and 20% testing sets.
* Standardized the features using `StandardScaler`.

### Model

A **Linear Regression** model was used to predict `median_house_value`.

### Results

* RMSE: **70,060.52**
* R² Score: **0.6254**

The model explains approximately 62.54% of the variation in the test-set target values.

An actual-versus-predicted visualization was also created to examine prediction performance.

## K-Means Clustering

### Preprocessing

The following numerical features were selected:

* Age
* Annual Income (k$)
* Spending Score (1-100)

The selected features were standardized using `StandardScaler`.

### Elbow Method

K-Means models were tested for K values from 1 to 10.

Based on the elbow plot, **K = 4** was selected as a reasonable number of clusters.

### Cluster Interpretation

The four clusters represent different combinations of customer age, income, and spending behavior.

* **Cluster 0:** Relatively older customers with moderate income and moderate spending.
* **Cluster 1:** Younger customers with higher income and high spending.
* **Cluster 2:** Younger customers with lower income and moderately high spending.
* **Cluster 3:** Customers with higher income and relatively low spending.

A 2D scatter plot was created using annual income and spending score to visualize the customer clusters.

## Project Structure

```text
vortextech-aiml-week3/
│
├── data/
│   ├── housing.csv
│   └── Mall_Customers.csv
│
├── notebooks/
│   └── VortexTech_Week3_Regression_Clustering.ipynb
│
├── .venv/
│
├── requirements.txt
└── README.md
```

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Jupyter Notebook

## How to Run

### 1. Clone the repository

```bash
git clone <https://github.com/AtiyaQazi/VortexTech-AI-ML-Week3>
cd vortextech-aiml-week3
```

### 2. Create and activate a virtual environment

```bash
python -m venv .venv
```

Windows PowerShell:

```powershell
.venv\Scripts\Activate.ps1
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Start Jupyter Notebook

```bash
jupyter notebook
```

Open:

`notebooks/VortexTech_Week3_Regression_Clustering.ipynb`

and run the notebook cells in order.

## Internship Submission

This repository contains the completed Week 3 regression and clustering project for the VortexTech AI & ML Internship.
