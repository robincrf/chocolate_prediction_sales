# Data Science Pipeline: Chocolate Sales Analysis

## Project Overview
This project demonstrates a complete **end-to-end Data Science pipeline**, developed as a technical assessment for a Data Scientist role. The objective is to process raw sales data, extract meaningful insights, and build a predictive model to estimate sales revenue.

The notebook showcases proficiency in data cleaning, feature engineering, exploratory data analysis (EDA), and machine learning implementation using Python.

## Key Skills Demonstrated

### 1. Data Engineering & Cleaning (Data Quality)
- **Robust Data Loading**: Securely loading data paths using environment variables (`python-dotenv`).
- **Data Sanitization**: Cleaning "dirty" columns (e.g., removing `$` and `,` from currency strings) and type conversion.
- **Date Handling**: Parsing and formatting raw date strings into usable `datetime` objects.
- **Quality Control**: Automated detection of missing values and logical inconsistencies (e.g., negative sales).

### 2. Feature Engineering
- **Temporal Analysis**: Extracting `Month` and `Year` features to analyze seasonality.
- **Categorical Simplification**: Creating broad `Product_Category` groups (e.g., "Dark Choco", "Nut Choco") from unstructured text descriptions using regex.
- **Unit Economics**: Deriving new metrics like `Price_Per_Box` to normalize sales performance.

### 3. Exploratory Data Analysis (EDA)
- **Seasonality & Trends**: Visualizing sales volume over time to identify peak periods.
- **Distribution Analysis**: Examining price distributions across different markets using Boxplots.
- **Correlation Study**: Investigating relationships between volume (`Boxes Shipped`) and revenue (`Amount`) to identify key drivers.

### 4. Machine Learning (Predictive Modeling)
- **Objective**: Predict the total `Amount` of a sale.
- **Features**: `Boxes Shipped`, `Country`, `Product_Category` (One-Hot Encoded).
- **Model**: Linear Regression (Scikit-Learn).
- **Evaluation**: Assessing model performance using **R²** and **RMSE** metrics.

## Technologies Used
- **Python 3.x**
- **Pandas & NumPy**: For efficient data manipulation and numerical operations.
- **Matplotlib & Seaborn**: For data visualization.
- **Scikit-Learn**: For predictive modeling and preprocessing.
- **Dotenv**: For managing configuration and secrets.

## Project Structure
- `main.ipynb`: The Jupyter Notebook containing the full analysis code.
- `enoncé.md`: The original problem statement and requirements.
- `.env`: Configuration file for the dataset path.

## How to Run
1. **Install Dependencies**: Ensure you have Python and the required libraries installed.
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn python-dotenv
   ```
2. **Configure Environment**: Create a `.env` file in the project root with the path to your dataset:
   ```
   CSV_PATH=../data/Chocolate_sales.csv
   ```
3. **Execute Notebook**: Open and run the cells in `main.ipynb`.

---
*Demonstration for Data Scientist Internship Evaluation*
