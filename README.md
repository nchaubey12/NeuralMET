# NeuralMET ‚Äî AI Adoption & Salary Analysis

This repository contains the NeuralMET analysis notebook (`nueramet.ipynb`), which explores how AI adoption metrics‚Äîsuch as productivity gains, workforce impact, role creation, and adoption year‚Äîrelate to salary outcomes across different countries and roles.

The notebook performs a full **EDA ‚Üí data cleaning ‚Üí feature engineering ‚Üí statistical testing ‚Üí correlation ‚Üí paired t-testing ‚Üí regression modeling ‚Üí trend analysis** workflow across merged datasets.

---

# üìå Project Overview
**Goal:**  
To analyze how Generative AI adoption metrics influence median salary outcomes across countries, roles, and years.

### **Main Research Hypothesis (H1)**  
Higher AI adoption indicators‚Äîsuch as productivity gain, employees impacted, new AI-related roles, and adoption year‚Äîare associated with **higher median salaries**.

### **Null Hypothesis (H0)**  
AI adoption metrics have **no meaningful relationship** with salary.

The notebook evaluates these hypotheses using statistical tests, correlation analysis, regression modeling, and trend visualizations.

---

# üìÇ Project Structure
```
‚îú‚îÄ‚îÄ dataframe/
‚îÇ   ‚îú‚îÄ‚îÄ jobs_in_data.csv           # Job-level salary dataset
‚îÇ   ‚îî‚îÄ‚îÄ enterprise_gen_ai.csv      # AI adoption metrics dataset
‚îú‚îÄ‚îÄ notebook/
‚îÇ   ‚îî‚îÄ‚îÄ nueramet.ipynb             # Full analysis notebook
‚îú‚îÄ‚îÄ LICENSE
‚îú‚îÄ‚îÄ README.md                      # Documentation (this file)
‚îî‚îÄ‚îÄ .DS_Store                      # System file (ignore)
```

---

# 1Ô∏è‚É£ Data Loading & Preprocessing
The notebook performs:

- Loading **two datasets**
- Viewing column names, shape, and data types
- Checking missing values
- Cleaning inconsistent country names
- Removing duplicates
- Dropping unnecessary columns (`experience_level`)
- Detecting outliers using the IQR method
- Extracting country-year median salary from `jobs_in_data.csv`
- Standardizing features for both datasets
- Merging the datasets into a final dataframe (`df_final`)

This ensures a clean, aligned dataset for statistical analysis and modeling.

---

# 2Ô∏è‚É£ Exploratory Data Analysis (EDA)
The notebook explores:

- Salary distributions and ranges  
- Unique work years and frequency  
- Outlier patterns using boxplots and IQR  
- Salary variation by:
  - Country  
  - Work year  
  - Job category  
- Highest salary outliers for quality inspection  

**Outcome:** Salary varies strongly across countries; AI metrics show much lower variance.

---

# 3Ô∏è‚É£ AI Adoption Feature Engineering
AI-related variables are prepared for modeling:

- Adoption Year  
- Productivity Change (%)  
- Employees Impacted  
- New New AI-Driven Roles  
- Country-level aggregation  
- Standardization of country names  
- Grouping of job categories into AI-related types  

These features form the basis for correlation, t-tests, and regression.

---

# 4Ô∏è‚É£ Statistical Testing

## **Normality (Shapiro‚ÄìWilk Test)**
Assesses normality of:

- Productivity Change (%)  
- Median Salary  
- Salary differences (2024 ‚àí 2022)

**Result:**  
No significant deviation from normality ‚Üí parametric tests are valid.

---

## **Pearson Correlation**
Correlates Median Salary with:

- Productivity Change  
- Employees Impacted  
- New Roles Created  
- Adoption Year  

**Findings:**

- AI adoption metrics show **weak or negligible correlation** with salary.
- Country effects dominate.

---

## **Paired t-Test (2022 vs 2024 Salaries)**

**Your notebook results:**
- t ‚âà **‚àí1.87**  
- p ‚âà **0.0977**

**Interpretation:**  
Not statistically significant at Œ± = 0.05.  
Direction suggests a possible **decrease** but cannot be confirmed.

---

# 5Ô∏è‚É£ Regression Modeling

Regression formula:
```
Median Salary ~ Productivity Change + Adoption Year + Employees Impacted + New Roles Created
```

Models used:

- Linear Regression  
- Ridge Regression  
- Lasso Regression  
- Random Forest Regression  

### **Regression Insights**
- Cross-validation R¬≤ is **near zero or negative**, indicating poor generalization.
- AI adoption variables **do not meaningfully predict salary**.
- Strong country-level differences overwhelm AI-related variance.
- Dataset size and uniformity limit predictive performance.

---

# 6Ô∏è‚É£ Trend Analysis (Year-over-Year)

Visualizations show salary trends from 2022 to 2024.

### **Trend Observations**
- Some countries show notable salary increases.
- Others exhibit stagnation or decline.
- These trends appear **country-specific**, not linked to AI metrics.

---

# üìä Summary of Statistical Techniques

| Technique | Purpose |
|----------|---------|
| Shapiro‚ÄìWilk | Test normality |
| Pearson Correlation | Assess linear relationships |
| Paired t-Test | Compare salary changes by year |
| Regression Modeling | Predict salary using AI adoption metrics |
| IQR Outlier Detection | Identify extreme values |
| General EDA | Understand variable distributions |

---

# üõ†Ô∏è Tools & Libraries Used
- Python 3  
- pandas  
- numpy  
- seaborn / matplotlib  
- scipy (Shapiro, Pearson, t-test)  
- scikit-learn (regression)  
- Jupyter Notebook / Google Colab  

---

# üìà Key Takeaways

### **1. Country is the strongest predictor of salary.**  
AI adoption metrics have a smaller effect.

### **2. Productivity Change (%) has no meaningful salary impact.**

### **3. No statistically significant salary difference between 2022 and 2024.**

### **4. Regression models cannot accurately predict salary with current features.**

### **5. Additional variables (industry, company size, job level, GDP, PPP, etc.) are needed for stronger predictive modeling.**

---

# üìú License
Choose MIT or another license depending on your project requirements.

---

# ü§ù Contributions
Contributions, feedback, and pull requests are welcome.

