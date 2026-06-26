<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=2C3E70&height=200&section=header&text=HR%20Workforce%20Analytics&fontSize=38&fontColor=FFFFFF&fontAlignY=38&desc=Power%20BI%20%7C%20People%20Analytics%20%7C%20Workforce%20Intelligence&descAlignY=58&descFontSize=16&descFontColor=FFD700" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Tool-Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black"/>
  <img src="https://img.shields.io/badge/Domain-Human%20Resources-2C3E70?style=for-the-badge&logo=googlescholar&logoColor=white"/>
  <img src="https://img.shields.io/badge/Dataset-50K%20Employees-28A745?style=for-the-badge&logo=databricks&logoColor=white"/>
  <img src="https://img.shields.io/badge/DAX%20Measures-29-E91E63?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Pages-3%20Dashboard%20Views-9C27B0?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge"/>
</p>

---

## 👥 Project Overview

This project delivers a **3-page Power BI people-analytics dashboard** built to help HR leadership and business stakeholders understand workforce composition, attrition drivers, and compensation patterns across a **50,000-employee organization**. The model is powered by a dedicated `_Measures` table containing **29 custom DAX measures**, covering everything from headcount and tenure to attrition rate, training spend, and pay equity.

> 💡 *Designed to turn raw HR transactional data into a single source of truth for headcount planning, retention strategy, and compensation review.*

---
## 🎥 Project Overview

🎬 Full walkthrough video → [Watch HR_Workforce_Analytics_Dashboard.mp4](https://drive.google.com/file/d/1CXA7hJQwpJrOLoKGdUBYeSvG6XpN8ENF/view?usp=sharing)


---

## 📸 Dashboard Preview

### 🧭 Page 1 — Workforce Overview
> *Snapshot of total/active headcount, tenure, training investment, gender mix, and career-level distribution*


---

### 📉 Page 2 — Attrition Analysis
> *YTD and rolling attrition rate, hiring trends vs. prior year, monthly new-hire pattern, and attrition hot-spots by department*


---

### 💰 Page 3 — Compensation & Training
> *Salary bands, performance distribution, department-wise pay ranking, and training cost allocation*

---

### 🔗 Data Model
> *Star-schema-style model connecting EmployeeMaster to Training, EngagementSurvey, Recruitment, Performance, and Dimdate*


---

## 🎯 Key Business KPIs

| Dashboard Page | KPI | Value |
|---|---|---|
| 🧭 Workforce Overview | Total Employees | 50,000 |
| 🧭 Workforce Overview | Active Employees | 24,554 |
| 🧭 Workforce Overview | Attrition Rate | **50.89%** |
| 🧭 Workforce Overview | Average Salary | $64,992.90 |
| 🧭 Workforce Overview | High Performers % | 100.00% |
| 🧭 Workforce Overview | Average Tenure | 5.42 years |
| 🧭 Workforce Overview | Training Investment | $2,79,31,625.56 |
| 🧭 Workforce Overview | Female % | 55.83% |
| 📉 Attrition Analysis | Attrition Rate (Filtered/Selected Year) | 10.59% |
| 📉 Attrition Analysis | Attrition Rate YTD | 21.67% |
| 📉 Attrition Analysis | Terminated Employees | 1,050 |
| 📉 Attrition Analysis | New Hires YoY % | 134.18% |
| 💰 Compensation | Active Headcount (Total) | 24,554 |
| 💰 Compensation | Avg Salary (Org-wide) | $64,992.90 |
| 💰 Compensation | Above vs Below Avg Salary Split | 50% / 50% |
| 💰 Compensation | Highest Training Cost Department | Production ($19M) |

---

## 🗄️ Data Model

The report is built on a relational model centered around a single fact-like hub table, **EmployeeMaster**, connected to five supporting tables:

| Table | Role | Key Fields |
|---|---|---|
| `EmployeeMaster` | Central hub table | EmpID, ADEmail, BusinessUnit, Career_Level_Band, Current Employee Rating, Days_Since_Hire, DepartmentType, Division, DOB |
| `Training` | Training records | Employee ID, Location, Trainer, Training Cost, Training Date, Training Duration (Days), Training Outcome, Training Program Name, Training Type |
| `EngagementSurvey` | Employee engagement data | Employee ID, Engagement Score, Satisfaction Score, Survey Date, Work-Life Balance Score |
| `Recruitment` | Hiring pipeline data | Applicant ID, Above_Avg_Salary_Flag, Address, Application Date, City, Country, Date of Birth, Desired Salary, Education Level |
| `Performance` | Performance review history | Employee ID, Employee Name, Current Employee Rating, Quarter, Year |
| `Dimdate` | Date dimension | Date, Month Name, Month Num, Quarter, Weekday, Year, Year_Quarter |

All tables relate back to `EmployeeMaster` via **Employee ID**, with `Dimdate` providing time intelligence across Training and Recruitment activity.

---

## 🧩 Dashboard Navigation

The report uses a custom left-hand navigation panel with three pages:

| Page | Focus Area |
|---|---|
| ⚙️ **Workforce Overview** | Headcount, tenure, training spend, gender mix, career-level bands |
| 🔁 **Attrition Analysis** | Attrition rate trends, hiring vs. terminations, department-wise attrition |
| 💵 **Compensation & Training** | Salary bands, performance distribution, training cost by department |

Global filters are available on every page: **Department**, **Career Level Band**, and **Year** (slicer/timeline).

---

## 📐 DAX Measures Library

All KPIs in this report are powered by a dedicated **`_Measures`** table containing **29 custom DAX measures**, organized below by analytical category for clarity.

### 👤 Headcount & Workforce Composition
| Measure | Purpose |
|---|---|
| `Total_Headcount` | Total employees across the entire dataset |
| `Total_HC_All_Depts` | Total headcount broken out across all departments |
| `Active_Headcount` | Count of currently active employees |
| `Senior_Headcount` | Count of employees in senior/experienced career bands |
| `Headcount_%_of_Total` | Department/segment headcount as a % of total workforce |
| `Distinct_Department` | Distinct count of departments represented |
| `Gender_Diversity_Ratio` | Male-to-female (or gender mix) ratio across the workforce |
| `Bench_Utilisation %` | % of workforce currently benched / non-billable |

### 🔁 Attrition & Retention
| Measure | Purpose |
|---|---|
| `Attrition_Rate %` | Overall attrition rate for the selected filter context |
| `Attrition_Rate_YTD` | Year-to-date attrition rate |
| `Terminated_Count` | Count of employees terminated/exited |
| `YTD_Terminations` | Year-to-date termination count |
| `Avg_Tenure` | Average employee tenure in years |

### 📈 Hiring Trends
| Measure | Purpose |
|---|---|
| `New_Hires` | Count of new hires in the selected period |
| `New_Hires_SPLY` | New hires for the same period last year (comparison baseline) |
| `New_Hires_YoY_%` | Year-over-year % change in new hires |
| `YTD_New_Hires` | Year-to-date new hire count |
| `Hires_Prior_3M` | New hires in the trailing 3-month window |

### 💵 Compensation & Pay Equity
| Measure | Purpose |
|---|---|
| `Avg_Salary` | Average salary across the selected workforce segment |
| `Highest_salary` | Maximum salary value in the filtered context |
| `Lowest_salary` | Minimum salary value in the filtered context |
| `Median_salary` | Median salary across the workforce |
| `Total_salary_cost` | Total organization-wide salary expenditure |
| `Salary_Rank_Dept` | Department ranking based on average salary |
| `Dept_Avg_Salary_AEXCEPT` | Department average salary (custom exception/edge-case logic) |

### 🎓 Performance & Training
| Measure | Purpose |
|---|---|
| `Avg_Performance_Rating` | Average performance rating across employees |
| `High_Performer_%` | % of workforce rated as high performers |
| `High_Performers_Count` | Absolute count of high-performing employees |
| `Avg_Training_Cost` | Average training cost per employee |
| `Total_Training_Cost` | Total organization-wide training investment |
| `Training_Cost_Rank` | Department ranking based on training cost |

> 📝 *Measure formulas (DAX expressions) are defined within the `.pbix` file's data model and can be inspected directly in Power BI Desktop under the `_Measures` table.*

---

## 🛠️ Technical Implementation

### ⚙️ Power Query Transformations
- Standardized data types across employee, department, and salary tables
- Derived **Career Level Band** (Beginner / Intermediate / Experienced) from tenure/level data
- Derived **Salary Band** (A/B/C/D) groupings for compensation analysis
- Built **Year-over-Year** and **Same-Period-Last-Year** comparison columns for hiring trend analysis
- Cleaned and standardized **Department Type** categories (Production, IT/IS, Sales, Software Engineering, Admin Offices, Executive Office)

### 🎨 Design Choices
- **Theme:** Navy blue (`#2C3E70`) corporate palette with gold/white accents
- **Navigation:** Custom icon-based left sidebar across all 3 pages
- **Visuals:** KPI cards, donut charts, horizontal bar charts, line/area trend charts, ranked matrix tables
- **Filters:** Department, Career Level Band, and Year slicer/timeline synced across pages
- **Comparative Analysis:** YoY and SPLY (same period last year) hiring comparisons built directly into visuals

---

## 💡 Key Insights Uncovered

### Workforce Overview
-  **Production** is by far the largest department with **17.0K active employees**, followed by IT/IS (3.5K) and Sales (2.7K)
-  The workforce skews slightly female at **55.83%**
-  Nearly half the workforce (**48.02%**) falls into the "Experienced" career level band
-  Average tenure stands at **5.42 years**, with a substantial training investment of **$2.79 Cr**

### Attrition Analysis
-  New hire volume has grown sharply, with **YoY growth of 134.18%** in the most recent period
-  **Admin Offices** has the highest department-level attrition rate at **27.19%**, nearly 3x higher than IT/IS (9.53%) — a clear retention red flag
-  Hiring is heavily back-loaded in the year, peaking in **September (9.1K)** and **March (9.9K)**
-  **1,050 employees** were terminated, pushing YTD attrition to **21.67%**

### Compensation & Training
-  Salary distribution is perfectly balanced — exactly **50% above and 50% below** the organization average
-  **Production** absorbs the largest share of training budget at **$19M**, dwarfing every other department combined
-  Performance ratings show **"Meets Expectations"** as the dominant category (12,605 of 24,554 employees), with Production driving the bulk of both top and bottom performance bands

---

## 🚀 How to Use

1. **Clone this repository**
   ```bash
   git clone https://github.com/HarshalVora86/HR_Workforce_Analytics_Dashboard_Power_BI.git
   ```

2. **Open the Power BI file**
   - Launch **Power BI Desktop** (free download from Microsoft)
   - Open `HR_Workforce_Analytics_Dashboard.pbix`

3. **Explore the model**
   - Expand the `_Measures` table in the Fields pane to inspect all 29 DAX formulas
   - Use **Model view** to review table relationships

4. **Navigate the 3 dashboard pages** using the left sidebar — Workforce Overview, Attrition Analysis, and Compensation & Training

---

## 🧰 Tools & Technologies

<p>
  <img src="https://img.shields.io/badge/Power%20BI%20Desktop-F2C811?style=flat-square&logo=powerbi&logoColor=black" height="28"/>
  &nbsp;
  <img src="https://img.shields.io/badge/DAX-0078D4?style=flat-square&logo=microsoftazure&logoColor=white" height="28"/>
  &nbsp;
  <img src="https://img.shields.io/badge/Power%20Query%20(M)-217346?style=flat-square&logo=microsoft&logoColor=white" height="28"/>
  &nbsp;
  <img src="https://img.shields.io/badge/Data%20Modeling-28A745?style=flat-square&logo=databricks&logoColor=white" height="28"/>
  &nbsp;
  <img src="https://img.shields.io/badge/People%20Analytics-2C3E70?style=flat-square&logo=googlescholar&logoColor=white" height="28"/>
</p>

---

## 👨‍💻 About the Author

**dhruv prajapati**


<p>
  <a href="https://github.com/HarshalVora86">
    <img src="https://img.shields.io/badge/GitHub-HarshalVora86-181717?style=for-the-badge&logo=github"/>
  </a>
  &nbsp;
<a href="https://www.linkedin.com/in/harshal-vora-344601251">   
 <img src="https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=for-the-badge&logo=linkedin"/>
  </a>
</p>

---

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=2C3E70&height=100&section=footer&fontColor=white"/>
</p>
