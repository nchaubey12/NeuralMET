# NeuralMET — AI Adoption & Salary Analysis

This repository contains the NeuralMET analysis notebook (⁠ nueramet.ipynb ⁠), which explores how AI adoption metrics—such as productivity gains, workforce impact, role creation, and adoption year—relate to salary outcomes across different countries and roles.

The notebook performs a full *EDA → data cleaning → feature engineering → statistical testing → correlation → paired t-testing → regression modeling → trend analysis* workflow across merged datasets.

---

# 📌 Project Overview
*Goal:*  
To analyze how Generative AI adoption metrics influence median salary outcomes across countries, roles, and years.

### *Main Research Hypothesis (H1)*  
Higher AI adoption indicators—such as productivity gain, employees impacted, new AI-related roles, and adoption year—are associated with *higher median salaries*.

### *Null Hypothesis (H0)*  
AI adoption metrics have *no meaningful relationship* with salary.

The notebook evaluates these hypotheses using statistical tests, correlation analysis, regression modeling, and trend visualizations.

---

# 📂 Project Structure

├── dataframe/
│   ├── jobs_in_data.csv           # Job-level salary dataset
│   └── enterprise_gen_ai.csv      # AI adoption metrics dataset
├── notebook/
│   └── nueramet.ipynb             # Full analysis notebook
├── LICENSE
├── README.md                      # Documentation (this file)
└── .DS_Store                      # System file (ignore)


---

# 1️⃣ Data Loading & Preprocessing
The notebook performs:

•⁠  ⁠Loading *two datasets*
•⁠  ⁠Viewing column names, shape, and data types
•⁠  ⁠Checking missing values
•⁠  ⁠Cleaning inconsistent country names
•⁠  ⁠Removing duplicates
•⁠  ⁠Dropping unnecessary columns (⁠ experience_level ⁠)
•⁠  ⁠Detecting outliers using the IQR method
•⁠  ⁠Extracting country-year median salary from ⁠ jobs_in_data.csv ⁠
•⁠  ⁠Standardizing features for both datasets
•⁠  ⁠Merging the datasets into a final dataframe (⁠ df_final ⁠)

This ensures a clean, aligned dataset for statistical analysis and modeling.

---

# 2️⃣ Exploratory Data Analysis (EDA)
The notebook explores:

•⁠  ⁠Salary distributions and ranges  
•⁠  ⁠Unique work years and frequency  
•⁠  ⁠Outlier patterns using boxplots and IQR  
•⁠  ⁠Salary variation by:
  - Country  
  - Work year  
  - Job category  
•⁠  ⁠Highest salary outliers for quality inspection  

*Outcome:* Salary varies strongly across countries; AI metrics show much lower variance.

---

# 3️⃣ AI Adoption Feature Engineering
AI-related variables are prepared for modeling:

•⁠  ⁠Adoption Year  
•⁠  ⁠Productivity Change (%)  
•⁠  ⁠Employees Impacted  
•⁠  ⁠New New AI-Driven Roles  
•⁠  ⁠Country-level aggregation  
•⁠  ⁠Standardization of country names  
•⁠  ⁠Grouping of job categories into AI-related types  

These features form the basis for correlation, t-tests, and regression.

---

# 4️⃣ Statistical Testing

## *Normality (Shapiro–Wilk Test)*
Assesses normality of:

•⁠  ⁠Productivity Change (%)  
•⁠  ⁠Median Salary  
•⁠  ⁠Salary differences (2024 − 2022)

*Result:*  
No significant deviation from normality → parametric tests are valid.

---

## *Pearson Correlation*
Correlates Median Salary with:

•⁠  ⁠Productivity Change  
•⁠  ⁠Employees Impacted  
•⁠  ⁠New Roles Created  
•⁠  ⁠Adoption Year  

*Findings:*

•⁠  ⁠AI adoption metrics show *weak or negligible correlation* with salary.
•⁠  ⁠Country effects dominate.

---

## *Paired t-Test (2022 vs 2024 Salaries)*

*Your notebook results:*
•⁠  ⁠t ≈ *−1.87*  
•⁠  ⁠p ≈ *0.0977*

*Interpretation:*  
Not statistically significant at α = 0.05.  
Direction suggests a possible *decrease* but cannot be confirmed.

---

# 5️⃣ Regression Modeling

Regression formula:

Median Salary ~ Productivity Change + Adoption Year + Employees Impacted + New Roles Created


Models used:

•⁠  ⁠Linear Regression  
•⁠  ⁠Ridge Regression  
•⁠  ⁠Lasso Regression  
•⁠  ⁠Random Forest Regression  

### *Regression Insights*
•⁠  ⁠Cross-validation R² is *near zero or negative*, indicating poor generalization.
•⁠  ⁠AI adoption variables *do not meaningfully predict salary*.
•⁠  ⁠Strong country-level differences overwhelm AI-related variance.
•⁠  ⁠Dataset size and uniformity limit predictive performance.

---

# 6️⃣ Trend Analysis (Year-over-Year)

Visualizations show salary trends from 2022 to 2024.

### *Trend Observations*
•⁠  ⁠Some countries show notable salary increases.
•⁠  ⁠Others exhibit stagnation or decline.
•⁠  ⁠These trends appear *country-specific*, not linked to AI metrics.

---

# 📊 Summary of Statistical Techniques

| Technique | Purpose |
|----------|---------|
| Shapiro–Wilk | Test normality |
| Pearson Correlation | Assess linear relationships |
| Paired t-Test | Compare salary changes by year |
| Regression Modeling | Predict salary using AI adoption metrics |
| IQR Outlier Detection | Identify extreme values |
| General EDA | Understand variable distributions |

---

# 🛠️ Tools & Libraries Used
•⁠  ⁠Python 3  
•⁠  ⁠pandas  
•⁠  ⁠numpy  
•⁠  ⁠seaborn / matplotlib  
•⁠  ⁠scipy (Shapiro, Pearson, t-test)  
•⁠  ⁠scikit-learn (regression)  
•⁠  ⁠Jupyter Notebook / Google Colab  

---

# 📈 Key Takeaways

### *1. Country is the strongest predictor of salary.*  
AI adoption metrics have a smaller effect.

### *2. Productivity Change (%) has no meaningful salary impact.*

### *3. No statistically significant salary difference between 2022 and 2024.*

### *4. Regression models cannot accurately predict salary with current features.*

### *5. Additional variables (industry, company size, job level, GDP, PPP, etc.) are needed for stronger predictive modeling.*

---

# 📜 License
Choose MIT or another license depending on your project requirements.

---

# 🤝 Contributions
Contributions, feedback, and pull requests are welcome.