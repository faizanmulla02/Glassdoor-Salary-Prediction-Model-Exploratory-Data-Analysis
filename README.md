# 💼 Glassdoor Data Analysis & Salary Prediction using ML

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)
![Status](https://img.shields.io/badge/Project-Completed-brightgreen)

## 📌 Project Summary

In today’s competitive job market, salary transparency plays a vital role in career planning and HR decisions. This project analyzes job listings from **Glassdoor** to uncover insights into salary trends across job titles, locations, company sizes, and more.

We also build a **Linear Regression Model** to predict salaries based on job-related features, applying various EDA and statistical testing techniques.

🔗 [GitHub Repository](https://github.com/faizanmulla02/faizanmulla02)

---

## 📊 Key Objectives

- 🔍 Perform Exploratory Data Analysis (EDA) on salary data
- 🧠 Build a salary prediction model using **Linear Regression**
- 🔎 Test hypotheses about salary, ratings, and job roles
- 📈 Visualize salary patterns using various charts
- 🧹 Preprocess textual data for modeling

---

## 📁 Dataset Overview

The dataset contains `956` tech job listings with the following key features:

| Column               | Description                                 |
|----------------------|---------------------------------------------|
| `Job Title`          | Role title (e.g., Data Scientist)           |
| `Salary Estimate`    | Salary range (e.g., $60K-$90K)              |
| `Rating`             | Company rating on Glassdoor                 |
| `Company Name`       | Name of the company                         |
| `Location`           | Job location                                |
| `Revenue`, `Size`    | Company revenue and size                    |
| `Job Description`    | Full job details (textual)                  |

---

## 🔧 Tech Stack

- `Python` 🐍
- `Pandas`, `NumPy` 🧮
- `Matplotlib`, `Seaborn` 📊
- `scikit-learn` ⚙️
- `NLTK` 🗣️
- `TfidfVectorizer` & `PCA` for NLP

---

## 📈 Exploratory Data Analysis

✅ Charts & Plots:
- ✅ Histogram of Salary Distributions
- ✅ Boxplot of Salaries by Job Title
- ✅ Countplot of Top Job Titles
- ✅ Swarm Plot: Salary vs Revenue
- ✅ Donut Chart: Sector Distribution
- ✅ Heatmap: Job Title Frequency by Location
- ✅ Correlation Matrix

📌 **Sample Code – Salary Distribution**

```python
sns.histplot(df['Min Salary'], kde=True, color='blue', label='Min Salary')
sns.histplot(df['Max Salary'], kde=True, color='green', label='Max Salary', alpha=0.5)
plt.title('Distribution of Min and Max Salaries')
plt.xlabel('Salary (in Thousands)')
plt.legend()
plt.show()
````
-----
## 🧪 Hypothesis Testing
1. Companies with higher ratings offer higher salaries
- 📌 Test: Independent t-test
- ✅ Result: p-value < 0.05 → Reject null hypothesis ✅

2. Correlation between Min & Max Salary
- 📌 Test: Pearson Correlation
- ✅ Result: Strong positive correlation (0.95)

3. Salary varies by Job Title
- 📌 Test: One-way ANOVA
- ✅ Result: p-value < 0.05 → Statistically significant
------
## ⚙️ Data Preprocessing
- ✅ Removed duplicates and nulls

- ✅ Cleaned Salary Estimate column

- ✅ Converted salary to Min, Max, and Avg

- ✅ Categorical Encoding: One-hot encoding

- ✅ Text Cleaning using NLTK (contractions, stopwords, POS, TF-IDF)
----
📌 **Sample Code – Converting Salary Ranges**
```python
def parse_salary(salary):
    parts = salary.split('-')
    return int(parts[0].strip()), int(parts[1].strip())

salary_df = df['Salary Estimate'].apply(lambda x: pd.Series(parse_salary(x)))
df[['Min Salary', 'Max Salary']] = salary_df
````
-----
## 📌 Results & Insights
- 💰 Data Scientist, ML Engineer roles have highest median salary

- 🏢 Larger companies offer better compensation

- 🌆 SF, NYC, Seattle lead in salary and job count

- 🔍 Strong correlation between Min and Max salary

- 🧠 Model performs reasonably well using basic features
-----
## 🧽 Text Preprocessing Techniques Used
- ✅ Expand contractions

- ✅ Lowercasing

- ✅ Remove punctuation, digits, URLs

- ✅ Remove stopwords

- ✅ Lemmatization

- ✅ POS tagging

- ✅ TF-IDF Vectorization
----
## 🚀 How to Run
```bash
# Step 1: Clone the repo
git clone https://github.com/faizanmulla02/faizanmulla02.git

# Step 2: Install dependencies
pip install -r requirements.txt

# Step 3: Run the analysis
python glassdoor_salary_prediction.py
```
----
## 📃 License
This project is licensed under the MIT License - see the LICENSE file for details.
