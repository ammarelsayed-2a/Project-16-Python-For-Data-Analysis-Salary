# Project-16-Python-For-Data-Analysis-Salary
End-to-end Salary Data Analysis on 22,770 tech industry records | Outlier detection using IQR, job role &amp; location salary comparison, correlation analysis &amp; dashboard using Python, Pandas &amp; Seaborn

# 💼 Salary Data Analysis — Tech Industry (22,000+ Records)

An end-to-end Salary Data Analysis project on 22,770 records from the Indian tech industry, completed as part of the **Python for Data Analysis** course.

## 📌 Objective
Complete data analysis workflow: cleaning, outlier detection using IQR method, salary distribution, job role & location comparisons, employment type analysis, correlation, trend analysis, bonus analytical questions, and a summary dashboard.

## 📂 Dataset
- **Source:** SalaryData.csv
- **Records:** 22,770 salary entries
- **Job Roles:** Android, Backend, Database, Frontend, iOS, Java, Mobile, SDE, Python, Web
- **Locations:** 10 Indian cities
- **Employment Types:** Full Time, Intern, Contractor, Trainee
- **Features:** Rating, Company, Job_Title, Salary, Salaries_Reported, Location, Employment_Status, Job_Role

## 🛠️ Tools & Libraries
| Library | Purpose |
|---|---|
| NumPy | IQR calculations & statistical operations |
| Pandas | Data loading, cleaning, groupby, aggregation |
| Matplotlib | Histograms, bar charts, line charts, dashboard |
| Seaborn | Boxplots, violin plots, heatmaps, scatter plots |

## 📋 Project Workflow

### Step 1 — Import Libraries
```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```
- **NumPy** — for IQR calculations and numerical operations
- **Pandas** — for loading, cleaning, and analyzing the dataset
- **Matplotlib** — for creating all chart types and the final dashboard
- **Seaborn** — for statistical visualizations (boxplots, heatmaps, violin plots)

### Step 2 — Load Dataset
```python
data = pd.read_csv('SalaryData.csv')
```
Load the CSV file into a Pandas DataFrame and verify the shape (22,770 rows × 8 columns).

### Step 3 — Data Understanding & EDA
- `head()` / `tail()` — first and last rows
- `shape` — number of rows and columns
- `dtypes` — data type of each column
- `info()` — non-null counts and memory usage
- `describe()` — statistical summary (mean, std, min, max, quartiles)
- `unique()` — unique values per categorical column

### Step 4 — Data Cleaning
- Detected 1 missing value in `Company Name` → removed with `dropna()`
- No duplicate rows found
- Renamed columns for cleaner code (e.g. `'Company Name'` → `'Company'`)

### Step 5 — Outlier Detection using IQR Method
```python
Q1 = data['Salary'].quantile(0.25)
Q3 = data['Salary'].quantile(0.75)
IQR = Q3 - Q1
Lower = Q1 - 1.5 * IQR
Upper = Q3 + 1.5 * IQR
data_clean = data[(data['Salary'] >= Lower) & (data['Salary'] <= Upper)]
```
- Max salary before: INR 9,00,00,000 (9 crore)
- Removed ~25% of records as statistical outliers
- Visualized with Boxplot before and after removal

### Step 6 — Salary Distribution
- Histogram + KDE of clean salary data
- Skewness, Mean, Median, Std

### Step 7 — Job Roles vs Salary
- Average salary per role (bar chart)
- Salary spread per role (boxplot)

### Step 8 — Location-based Salary Analysis
- Average salary per city (bar chart)
- Salary distribution per city (violin plot)
- Job Role × Location heatmap

### Step 9 — Company Rating vs Salary
- Scatter plot + Regression line
- Average salary per rating bucket (line chart)

### Step 10 — Employment Type Comparison
- Count and average salary per type (bar charts)
- Salary spread per type (boxplot)

### Step 11 — Correlation Analysis
- Correlation matrix between Rating, Salary, Salaries_Reported
- Heatmap visualization

### Step 12 — Trend Analysis
- Line chart: avg salary per job role across locations
- Heatmap: Job Role × Location

### Step 13 — Bonus Analytical Questions (Q1 → Q10)

| # | Question |
|---|---|
| Q1 | Most common Job Role in the dataset |
| Q2 | Top 10 companies with highest average salary |
| Q3 | Salary range (min/max/mean) per Employment Type |
| Q4 | Location with most job opportunities |
| Q5 | % of Full Time vs other employment types |
| Q6 | Job Role with highest number of salary reports |
| Q7 | Avg company rating per location |
| Q8 | Best Job Role + Location combination by salary |
| Q9 | Salary difference: High-rated (≥4.0) vs Low-rated (<4.0) companies |
| Q10 | Salary distribution per Job Role in Bangalore specifically |

### Step 14 — Dashboard
6-panel summary chart using `plt.subplots(2, 3)` covering all key dimensions.

## 💡 Key Insights
- Max salary was INR 9 crore — IQR method removed ~25% as outliers
- SDE commands the highest average salary among all job roles
- Bangalore and Mumbai lead in salary levels
- Full Time employees earn significantly more than Interns/Trainees
- Company rating has weak positive correlation with salary
- Salary distribution remains right-skewed even after outlier removal

## 🚀 How to Run
```bash
git clone https://github.com/ammarelsayed-2a/Project-16-Python-For-Data-Analysis-Salary.git
cd Project-16-Python-For-Data-Analysis-Salary
jupyter notebook "Project 16 Salary.ipynb"
```

## 👤 Author
**Ammar Elsayed** — Python for Data Analysis | 2026  
[LinkedIn](https://www.linkedin.com/in/ammar-elsayed-ibrahim)
