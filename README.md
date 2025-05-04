Penn State University

College of IST

DS 220-02/555v– Project #2 on Data Analysis with Python – Individual
(Team)

Compiled by Dr. Mathias Fonkam (Instructor)

Project #2 – Data Analysis with Python – An Individual or Team (max 6) Project which you
should each host on your individual Github Account

The broad goal for your Project #2 is to demonstrate some understanding and appreciation for
data analysis using Python and its growing suite of Data Science libraries with a special focus on
the Pandas library. The Pandas library builds on the NumPy and MatPlotlib libraries. In particular
you are required to:

• Identify a raw public dataset of interest to you to employ in your data analytics.

• Download the dataset to your computer and take some time to familiarize yourself with the
raw data and application area.

• Frame some 6 to 10 Questions that you or others in the area may want to answer analyzing
this data.

• Load your data set into a Pandas data frame and do some preprocessing and cleaning if
needed (this should be documented)

• Perform exploratory data analysis & visualization

• Implement your questions as queries on the Pandas dataframe to generate answers making
sure to documenting each code cells implementing each answer.

• Derive insight(s) using answers to your questions

• Communicates those insights as actionable text or a story that may be easy to communicate
and share with others interested in the same dataset.

• Publish your work on github pages at a reachable URL
Project Deliverable & Format
Deliverable: URL of your own GitHub Pages site hosting an .ipynb/.html export of your final
tutorial



# 🗂️ Employee Payroll Analysis with Python (DS 220‑02 Project #2)



## 📑 Project Overview
This project demonstrates an end‑to‑end data‑analysis workflow in Python using **Pandas** and **Matplotlib**.  
We explore a public dataset of **~700 k quarterly payroll records** for municipal employees, answer eight business‑driven questions, visualize key trends, and derive actionable insights for HR and Finance.

---

## 🔍 Dataset
| Property                 | Value                                                |
|--------------------------|------------------------------------------------------|
| Source                   | City of *philadelphia* Public Salaries Portal        |
| File                     | `employee_earnings.csv`                              |
| Rows                     | 711,117                                              |
| Time span                | 2019 – 2023 (calendar years)                         |
| Granularity              | *Employee × Quarter* (one row per employee‑quarter)  |
| Key fields               | `base_gross_pay_qtd`, `overtime_gross_pay_qtd`, `department_name`, `title`, `calendar_year`, etc. |

---

## 🧼 Data‑Cleaning Steps
1. **Drop** empty geometry columns (`the_geom`, `the_geom_webmercator`) and internal IDs.  
2. **Remove duplicates** and rows lacking critical fields (`base_gross_pay_qtd`, `title`, `department_name`).  
3. **Impute** non‑critical missing values:  
   *Categorical* → `Unknown`; *numeric pay fields* → `0`.  
4. **Filter** out implausible base‑pay rows ( < \$0 or > \$500 k per quarter).  
5. **Feature engineering**:  
   * `total_pay_qtd` = base + OT + longevity + misc pay  
   * `ot_share` = overtime / total compensation  
6. `.copy()` used after filtering to avoid `SettingWithCopyWarning`.

---

## ❓ Analytical Questions
1. **Total payroll growth** 2019 – 2023  
2. **Highest‑pay departments** and their overtime reliance  
3. **Average overtime share** of compensation  
4. **Share of quarters** with ≥ 10 % overtime  
5. **Top‑10 job titles** by median total pay  
6. **Tenure impact** of high overtime (≥ 25 %)  
7. **Seasonality** — average pay by quarter  
8. **Largest YOY overtime surge** by department (2022 → 2023)

---

## 📊 Exploratory Data Analysis
The notebook generates eight visuals:

| # | Chart/Table | Purpose |
|---|-------------|---------|
| 1 | Histogram of base pay | Skew & typical range |
| 2 | Histogram of total pay | Effect of OT & extras |
| 3 | Year‑by‑year total comp bar chart | Payroll growth trend |
| 4 | Bar chart of avg pay by quarter | Seasonality |
| 5 | Horizontal bar (top‑15 depts) | Pay equity across departments |
| 6 | Histogram of OT share | OT distribution |
| 7 | Scatter: base vs OT pay | Relationship between the two |
| 8 | Dept‑level OT vs base table | Identify OT‑heavy depts |

---

## 🧠 Key Insights
* **Payroll up 18 %** from 2019→2023, exceeding CPI.  
* **Public‑safety units dominate** both base pay and overtime → potential staffing review.  
* **13 % of quarters** exceed 10 % overtime → workload hotspot.  
* **High‑OT employees** stay ~4 years vs 5 years overall → retention risk.  
* **Department of Building Inspection** saw the **largest +\$5.4 M OT spike** in 2023.  
* **Q2 & Q4** run ~5 % higher pay → budget for seasonal peaks.



