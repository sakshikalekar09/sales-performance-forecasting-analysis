# Sales-Performance-Forecasting-Analysis
End-to-end sales performance and forecasting analysis using Python, Pandas, NumPy, Matplotlib, Seaborn, and Scikit-learn, including data cleaning, EDA, statistical analysis, visualizations, monthly sales forecasting, model evaluation, and business recommendations.


 ## Project Overview

This project focuses on analyzing historical sales data and predicting monthly sales using **Machine Learning**.
The project uses a Superstore-style sales dataset containing information about orders, customers, products, regions, categories, order dates, shipping dates, and sales.
The main objective is to clean the data, perform exploratory data analysis (EDA), create useful features from dates, and build a **Linear Regression** model for monthly sales prediction.

---

## Objectives

* Clean and prepare the sales dataset
* Handle missing values and check duplicate records
* Convert date columns into proper datetime format
* Perform Exploratory Data Analysis (EDA)
* Analyze monthly sales trends
* Create useful time-based features
* Build a Linear Regression model
* Evaluate model performance using R², RMSE, and MAE
* Compare actual and predicted monthly sales

---

## Dataset

The dataset contains **9,800 records and 18 columns**.
Important columns include:
* Row ID
* Order ID
* Order Date
* Ship Date
* Ship Mode
* Customer ID
* Customer Name
* Segment
* Country
* City
* State
* Postal Code
* Region
* Product ID
* Category
* Sub-Category
* Product Name
* Sales

---

##  Data Cleaning

The following data-cleaning steps were performed:

### Missing Values

The `Postal Code` column contained **11 missing values**.
Since Postal Code is a numerical column and only a small number of values were missing, the missing values were filled using the **median**.
```python
df["Postal Code"] = df["Postal Code"].fillna(
    df["Postal Code"].median()
)
```
After this step, there were no missing values remaining.

### Duplicate Values
Duplicate records were checked, and the dataset contained **0 duplicate rows**.

### Date Conversion
`Order Date` and `Ship Date` were converted from text format into datetime format.

---

##  Feature Engineering

Additional features were created from the date columns:
* `Shipping Days` – Number of days between order and shipping
* `Year` – Year of the order
* `Month_Number` – Month number
* `Month` – Monthly period used for sales analysis
These features help identify patterns and trends in the sales data.

---

## Exploratory Data Analysis

EDA was performed to understand the sales data and identify patterns.
The analysis includes:
* Monthly sales trends
* Sales distribution
* Sales by category
* Sales by region
* Sales-related visualizations
* Actual vs predicted monthly sales

---

##  Machine Learning Model

### Linear Regression
A **Linear Regression** model was used to predict monthly sales.
The dataset was divided into:
* **Training:** 38 months
* **Testing:** 10 months

The model was trained using the training data and then used to predict sales for the testing period.
```python
model = LinearRegression()
model.fit(X_train, y_train)
prediction = model.predict(X_test)
```
---

##  Model Evaluation
The model was evaluated using three metrics:

| Metric   |    Result |
| -------- | --------: |
| R² Score |     0.637 |
| RMSE     | 14,478.82 |
| MAE      | 10,520.28 |

### What these metrics mean

**R² Score:** Measures how well the model explains the variation in sales. A value of 0.637 means the model explains approximately 63.7% of the variation in the target.

**RMSE:** Measures the average size of prediction errors, giving more weight to larger errors.

**MAE:** Measures the average absolute difference between actual and predicted sales.

---

##  Technologies Used
* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Jupyter Notebook

---

##  Project Structure
```text
sales-performance-forecasting-analysis
│
├── README.md
├── requirements.txt
├── sales_forecasting.ipynb
└── train.csv
```
Make sure you upload train.csv only if you are allowed to share the dataset publicly.

---

## ▶️ How to Run the Project

### 1. Clone the repository
```bash
git clone https://github.com/your-username/sales-forecasting-linear-regression.git
```

### 2. Open the project folder
```bash
cd sales-forecasting-linear-regression
```

### 3. Install the required libraries
```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

### 4. Start Jupyter Notebook
```bash
jupyter notebook
```

### 5. Open the notebook
Open:
```text
Assesment Task.ipynb
```
Make sure `train.csv` is in the same folder as the notebook before running the cells.

---

##  Key Takeaways

* The dataset was successfully cleaned and prepared for analysis.
* Missing Postal Code values were handled using median imputation.
* No duplicate records were found.
* Date-based features were created for monthly sales analysis.
* Linear Regression was used for monthly sales prediction.
* The model achieved an R² score of **0.637** on the test data.
---

##  Author

**Sakshi Kalekar**
This project was created as a Machine Learning / Data Analysis project demonstrating data cleaning, exploratory data analysis, feature engineering, and sales prediction.

---

## If you find this project useful
Feel free to explore, improve, and experiment with different machine learning models and features to improve the sales prediction performance.

