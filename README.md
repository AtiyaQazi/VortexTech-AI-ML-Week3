# VortexTech AI & ML Internship-Week 3

## Regression and Clustering on Real Data

This project was completed as part of the **VortexTech AI & ML Internship-Week 3**.

The project demonstrates both **supervised and unsupervised machine learning** techniques using real-world datasets. It covers data inspection, cleaning, preprocessing, regression modeling, model evaluation, K-Means clustering, visualization, and interpretation.

---

## Project Objectives

The main objectives of this project are to:

* Build a regression model for a continuous numeric target.
* Perform data cleaning and preprocessing.
* Split data into training and testing sets.
* Train a Linear Regression model.
* Evaluate the regression model using **RMSE and R² Score**.
* Apply **K-Means clustering** to customer data.
* Scale clustering features using `StandardScaler`.
* Use the **Elbow Method** to determine a reasonable number of clusters.
* Visualize customer clusters in 2D.
* Interpret the resulting customer segments in real-world terms.

---

# Datasets

## 1. California Housing Dataset

**File:**

```text
data/housing.csv
```

The California Housing dataset is used for the regression task.

### Target Variable

```text
median_house_value
```

The target is a continuous numeric value representing the median house value.

The dataset contains housing-related numerical features along with the categorical feature:

```text
ocean_proximity
```

---

## 2. Mall Customers Dataset

**File:**

```text
data/Mall_Customers.csv
```

The Mall Customers dataset is used for the K-Means clustering task.

### Clustering Features

* `Age`
* `Annual Income (k$)`
* `Spending Score (1-100)`

`CustomerID` was excluded because it is an identifier and does not represent a meaningful customer characteristic.

`Genre` was excluded because this clustering analysis focuses on numerical customer characteristics.

---

# Part 1 — Regression

## Data Preprocessing

The California Housing dataset was inspected and cleaned before model training.

The preprocessing steps included:

* Checking dataset shape and columns.
* Checking data types.
* Checking missing values.
* Checking duplicate records.
* Filling missing `total_bedrooms` values using the column median.
* Applying one-hot encoding to the categorical `ocean_proximity` feature.
* Separating the features and continuous target variable.
* Splitting the dataset into training and testing sets using an **80/20 split**.
* Standardizing the features using `StandardScaler`.

---

## Regression Model

A **Linear Regression** model was selected for the regression task because the target variable, `median_house_value`, is continuous and numeric.

The model was trained using the training dataset and then used to predict house values for the unseen test dataset.

```python
model.fit(X_train_scaled, y_train)

y_pred = model.predict(X_test_scaled)
```

---

## Regression Evaluation

The model was evaluated using two metrics:

### RMSE

**Root Mean Squared Error (RMSE)** measures the magnitude of prediction errors. Lower values indicate smaller prediction errors.

### R² Score

**R² Score** measures the proportion of variation in the target variable explained by the regression model.

### Results

| Metric   |        Result |
| -------- | ------------: |
| RMSE     | **70,060.52** |
| R² Score |    **0.6254** |

The model explains approximately **62.54% of the variation** in the test-set median house values.

An **Actual vs Predicted** visualization was also created to compare the model's predictions with the actual house values.

---

# Part 2 — K-Means Clustering

## Feature Selection

Three numerical features were selected for customer clustering:

* `Age`
* `Annual Income (k$)`
* `Spending Score (1-100)`

These features provide useful information about customer demographics, income, and spending behavior.

---

## Feature Scaling

Because K-Means is a distance-based algorithm, the selected features were standardized using:

```python
StandardScaler()
```

This ensures that features with different numerical ranges have a more comparable influence on the clustering process.

---

# Elbow Method

The **Elbow Method** was used to determine a reasonable number of clusters.

K-Means models were tested using cluster counts from:

```text
K = 1 to K = 10
```

For each value of K, the model's **inertia** was recorded.

The inertia values were plotted against the number of clusters to identify the point where the reduction in inertia begins to slow down.

### Selected Number of Clusters

Based on the elbow plot:

**K = 4** was selected as a reasonable number of clusters.

Four clusters provide a practical balance between reducing within-cluster variation and keeping the customer segmentation understandable.

---

# Customer Cluster Analysis

The final K-Means model was trained using four clusters.

The resulting customer groups were analyzed using their average age, annual income, and spending score.

### Cluster 0

Relatively older customers with moderate income and moderate spending behavior.

### Cluster 1

Younger customers with higher income and high spending activity.

### Cluster 2

Younger customers with lower income and moderately high spending behavior.

### Cluster 3

Customers with higher income and relatively low spending activity.

These clusters provide a simplified segmentation of customers based on their demographic and spending characteristics.

In a real-world business environment, these segments could support customer analysis and help inform marketing and customer engagement strategies.

---

# Visualizations

The project includes the following visualizations:

### Regression

* Actual vs Predicted House Values

### Clustering

* Elbow Method Plot
* 2D Customer Cluster Scatter Plot

The 2D clustering visualization uses:

* **Annual Income (k$)** on the X-axis
* **Spending Score (1-100)** on the Y-axis

Each customer is assigned a cluster label and displayed according to its cluster.

---

# Project Structure

```text
VortexTech-AI-ML-Week3/
│
├── data/
│   ├── housing.csv
│   └── Mall_Customers.csv
│
├── notebooks/
│   └── VortexTech_Week3_Regression_Clustering.ipynb
│
├── .gitignore
├── README.md
└── requirements.txt
```

---

# Technologies Used

* **Python**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Seaborn**
* **Scikit-learn**
* **Jupyter Notebook**

---

# How to Run

## 1. Clone the Repository

```bash
git clone https://github.com/AtiyaQazi/VortexTech-AI-ML-Week3.git
cd VortexTech-AI-ML-Week3
```

## 2. Create a Virtual Environment

```bash
python -m venv .venv
```

### Windows PowerShell

```powershell
.venv\Scripts\Activate.ps1
```

## 3. Install Dependencies

```bash
pip install -r requirements.txt
```

## 4. Start Jupyter Notebook

```bash
jupyter notebook
```

Open:

```text
notebooks/VortexTech_Week3_Regression_Clustering.ipynb
```

Run the notebook cells in order from beginning to end.

--- 

## Author

**Attia Qaamar-un-nisa**
