<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=2,12,19,24,30&height=220&section=header&text=HR%20Workforce%20Analytics&fontSize=42&fontColor=FFFFFF&fontAlignY=36&desc=Power%20BI%20%7C%20People%20Analytics%20%7C%20Workforce%20Intelligence&descAlignY=58&descFontSize=17&descFontColor=FFD700&animation=fadeIn" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Tool-Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black"/>
  <img src="https://img.shields.io/badge/Domain-Human%20Resources-2C3E70?style=for-the-badge&logo=googlescholar&logoColor=white"/>
  <img src="https://img.shields.io/badge/Dataset-50K%20Employees-28A745?style=for-the-badge&logo=databricks&logoColor=white"/>
  <img src="https://img.shields.io/badge/DAX%20Measures-29-E91E63?style=for-the-badge&logo=microsoftazure&logoColor=white"/>
  <img src="https://img.shields.io/badge/Pages-3%20Dashboard%20Views-9C27B0?style=for-the-badge&logo=windowsterminal&logoColor=white"/>
  <img src="https://img.shields.io/badge/Status-Completed-00C853?style=for-the-badge&logo=checkmarx&logoColor=white"/>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Schema-Star%20Schema-FF6D00?style=flat-square&logo=databricks&logoColor=white"/>
  <img src="https://img.shields.io/badge/Tables-6%20Relational%20Tables-0078D4?style=flat-square&logo=microsoftsqlserver&logoColor=white"/>
  <img src="https://img.shields.io/badge/Time%20Intelligence-YoY%20%7C%20YTD%20%7C%20SPLY-8E24AA?style=flat-square&logo=googleanalytics&logoColor=white"/>
  <img src="https://img.shields.io/badge/Filters-Cross%20Page%20Sync-00897B?style=flat-square&logo=googleoptimize&logoColor=white"/>
</p>

---


---

## 👥 Project Overview

This project delivers a **3-page Power BI people-analytics dashboard** built to help HR leadership and business stakeholders understand workforce composition, attrition drivers, and compensation patterns across a **50,000-employee organization**.

The report is powered by a dedicated `_Measures` table containing **29 custom DAX measures** — covering everything from headcount and tenure to attrition rate, training spend, and pay equity — all wired into a clean **star-schema data model** across 6 relational tables.

> 💡 *Designed to turn raw HR transactional data into a single source of truth for headcount planning, retention strategy, and compensation review.*

### 🎯 Business Goals This Dashboard Solves

| Business Question | Dashboard Page |
|---|---|
| How many employees are active vs. total, and how are they distributed? | 🧭 Workforce Overview |
| Which departments are losing people fastest, and when do hires peak? | 📉 Attrition Analysis |
| Are we paying fairly? Who's performing, and where is training spend going? | 💰 Compensation & Training |

---

## 📸 Dashboard Preview

### 🧭 Page 1 — Workforce Overview
> *Snapshot of total/active headcount, tenure, training investment, gender mix, and career-level distribution across all departments and business units*


**Visuals on this page:**
- KPI cards — Total Employees, Active Headcount, Avg Salary, Avg Tenure, Attrition Rate, Female %, High Performers %, Training Investment
- Donut chart — Gender distribution
- Horizontal bar chart — Active headcount by department
- Stacked bar — Career level band breakdown (Beginner / Intermediate / Experienced)
- Matrix — Department-wise headcount vs. attrition rate comparison

---

### 📉 Page 2 — Attrition Analysis
> *YTD and rolling attrition rate, hiring trends vs. prior year, monthly new-hire pattern, and attrition hot-spots by department*


**Visuals on this page:**
- KPI cards — Attrition Rate %, Attrition Rate YTD, Terminated Count, New Hires YoY %
- Line/area chart — Monthly new hires trend (current year vs. prior year)
- Clustered column chart — Hires vs. terminations by month
- Horizontal bar — Department-level attrition rate ranking
- Slicer — Year filter driving all trend visuals

---

### 💰 Page 3 — Compensation & Training
> *Salary bands, performance distribution, department-wise pay ranking, and training cost allocation*


**Visuals on this page:**
- KPI cards — Active Headcount, Avg Salary, Above/Below Avg Salary split
- Donut chart — Performance rating distribution
- Horizontal bar — Department salary ranking (avg salary by dept)
- Bar chart — Training cost by department
- Matrix — Salary band (A/B/C/D) vs. career level cross-tab

---

### 🔗 Data Model View
> *Star-schema-style model connecting EmployeeMaster to Training, EngagementSurvey, Recruitment, Performance, and Dimdate*



## 🎯 Key Business KPIs

### 🧭 Page 1 — Workforce Overview

| KPI | Value | Notes |
|---|---|---|
| 👥 Total Employees | **50,000** | Full dataset |
| ✅ Active Employees | **24,554** | Currently employed |
| 📉 Attrition Rate | **50.89%** | Overall (all-time) |
| 💵 Average Salary | **$64,992.90** | Org-wide average |
| ⭐ High Performers % | **100.00%** | All rated employees |
| 🕐 Average Tenure | **5.42 years** | Across active workforce |
| 🎓 Training Investment | **$2,79,31,625.56** | Total training spend |
| 🚺 Female % | **55.83%** | Gender diversity metric |

### 📉 Page 2 — Attrition Analysis

| KPI | Value | Notes |
|---|---|---|
| 📉 Attrition Rate (Selected Year) | **10.59%** | Filtered year context |
| 📅 Attrition Rate YTD | **21.67%** | Year-to-date |
| 🚪 Terminated Employees | **1,050** | Count of exits |
| 📈 New Hires YoY % | **+134.18%** | Strong hiring ramp |

### 💰 Page 3 — Compensation & Training

| KPI | Value | Notes |
|---|---|---|
| 👥 Active Headcount | **24,554** | Filter-context driven |
| 💵 Avg Salary (Org-wide) | **$64,992.90** | All departments |
| ⚖️ Above vs Below Avg Salary | **50% / 50%** | Perfect pay balance |
| 🏭 Highest Training Cost Dept | **Production — $19M** | Largest training spend |

---

## 🗄️ Data Model

The report is built on a **star-schema relational model** centered on a single fact-like hub table — **EmployeeMaster** — connected to five supporting dimension/activity tables. All relationships flow through **Employee ID**, with `Dimdate` providing time intelligence for trend analysis.

```
                    ┌─────────────────┐
         ┌──────────│  EmployeeMaster │──────────┐
         │          │   (Hub / Fact)  │          │
         │          └────────┬────────┘          │
         │                   │                   │
    ┌────▼────┐         ┌─────▼──────┐    ┌──────▼──────┐
    │Training │         │Performance │    │  Recruitment│
    │(Activity)│        │  (Reviews) │    │  (Pipeline) │
    └─────────┘         └────────────┘    └─────────────┘
         │                   │
    ┌────▼──────────┐  ┌─────▼──────┐
    │EngagementSurvey│  │  Dimdate   │
    │  (Sentiment)  │  │(Time Intel)│
    └───────────────┘  └────────────┘
```

### Table Reference

| Table | Role | Key Fields |
|---|---|---|
| `EmployeeMaster` | Central hub — one row per employee | EmpID, ADEmail, BusinessUnit, Career_Level_Band, Current Employee Rating, Days_Since_Hire, DepartmentType, Division, DOB, Employment_Status |
| `Training` | Training activity records | Employee ID, Training Program Name, Training Type, Training Cost, Training Date, Training Duration (Days), Training Outcome, Trainer, Location |
| `EngagementSurvey` | Employee sentiment & satisfaction | Employee ID, Engagement Score, Satisfaction Score, Work-Life Balance Score, Survey Date |
| `Recruitment` | Hiring pipeline and candidate data | Applicant ID, Application Date, Education Level, Desired Salary, Above_Avg_Salary_Flag, City, Country, Date of Birth |
| `Performance` | Quarterly performance review history | Employee ID, Employee Name, Current Employee Rating, Quarter, Year |
| `Dimdate` | Date dimension for time intelligence | Date, Month Name, Month Num, Quarter, Weekday, Year, Year_Quarter |

> 🔗 All dimension/activity tables connect to `EmployeeMaster` via **Employee ID** (many-to-one). `Dimdate` links to `Training` and `Recruitment` date columns for YoY/YTD calculations.

---

## 🧩 Dashboard Navigation

The report uses a **custom icon-based left-hand navigation panel** that persists identically across all 3 pages, giving users a consistent one-click way to switch views without losing filter context.

| Icon | Page | What You'll Find |
|---|---|---|
| ⚙️ | **Workforce Overview** | Headcount totals, tenure distribution, gender mix, career-level bands, training spend summary |
| 🔁 | **Attrition Analysis** | Attrition rate (overall + YTD), monthly hire trends, YoY hiring comparison, dept-level attrition ranking |
| 💵 | **Compensation & Training** | Salary band analysis, pay equity split, performance distribution, training cost by department |

### 🔽 Global Filters (Synced Across All Pages)

| Filter | Type | Impact |
|---|---|---|
| **Department** | Dropdown slicer | Filters all visuals on current page |
| **Career Level Band** | Tile slicer (Beginner / Intermediate / Experienced) | Narrows workforce segment |
| **Year** | Timeline / dropdown | Drives YoY, YTD, and trend calculations |

---

## 📐 DAX Measures Library

All KPIs are powered by a dedicated **`_Measures`** table with **29 custom DAX measures**, built with filter-context awareness and time intelligence for accurate slicing across departments, career bands, and years.

### 👤 Headcount & Workforce Composition (8 measures)

| Measure | DAX Logic | Business Purpose |
|---|---|---|
| `Total_Headcount` | `COUNTROWS(EmployeeMaster)` | Total employees across entire dataset |
| `Total_HC_All_Depts` | `CALCULATE([Total_Headcount], ALL(Dept))` | Dept headcount ignoring dept filter |
| `Active_Headcount` | `CALCULATE(COUNTROWS(...), Status="Active")` | Count of currently active employees |
| `Senior_Headcount` | `CALCULATE(..., Band="Experienced")` | Employees in senior career bands |
| `Headcount_%_of_Total` | `DIVIDE([Active_Headcount],[Total_HC_All_Depts])` | Dept share of total workforce |
| `Distinct_Department` | `DISTINCTCOUNT(DepartmentType)` | Count of unique departments |
| `Gender_Diversity_Ratio` | `DIVIDE(Female Count, Total)` | Female % of workforce |
| `Bench_Utilisation %` | `DIVIDE(Benched, Active)` | Non-billable / bench utilisation |

### 🔁 Attrition & Retention (5 measures)

| Measure | DAX Logic | Business Purpose |
|---|---|---|
| `Attrition_Rate %` | `DIVIDE([Terminated_Count],[Total_Headcount])` | Overall attrition for filter context |
| `Attrition_Rate_YTD` | `CALCULATE([Attrition_Rate %], DATESYTD(...))` | Year-to-date attrition |
| `Terminated_Count` | `CALCULATE(COUNTROWS(...), Status="Terminated")` | Count of exits |
| `YTD_Terminations` | `CALCULATE([Terminated_Count], DATESYTD(...))` | YTD exit count |
| `Avg_Tenure` | `AVERAGEX(EmployeeMaster, Days_Since_Hire/365)` | Average years of service |

### 📈 Hiring Trends (5 measures)

| Measure | DAX Logic | Business Purpose |
|---|---|---|
| `New_Hires` | `CALCULATE(COUNTROWS(Recruitment), period filter)` | New hires in selected period |
| `New_Hires_SPLY` | `CALCULATE([New_Hires], SAMEPERIODLASTYEAR(...))` | Hires — same period last year |
| `New_Hires_YoY_%` | `DIVIDE([New_Hires]-[New_Hires_SPLY],[New_Hires_SPLY])` | YoY hiring growth % |
| `YTD_New_Hires` | `CALCULATE([New_Hires], DATESYTD(...))` | Year-to-date new hires |
| `Hires_Prior_3M` | `CALCULATE([New_Hires], DATESINPERIOD(...,-3,MONTH))` | Trailing 3-month hires |

### 💵 Compensation & Pay Equity (7 measures)

| Measure | DAX Logic | Business Purpose |
|---|---|---|
| `Avg_Salary` | `AVERAGE(EmployeeMaster[Salary])` | Avg salary — filter context |
| `Highest_salary` | `MAX(EmployeeMaster[Salary])` | Max salary in context |
| `Lowest_salary` | `MIN(EmployeeMaster[Salary])` | Min salary in context |
| `Median_salary` | `MEDIAN(EmployeeMaster[Salary])` | Median salary |
| `Total_salary_cost` | `SUM(EmployeeMaster[Salary])` | Total salary expenditure |
| `Salary_Rank_Dept` | `RANKX(ALL(Dept),[Avg_Salary],,DESC)` | Dept rank by avg salary |
| `Dept_Avg_Salary_AEXCEPT` | Custom `CALCULATE` with `ALLEXCEPT` | Dept avg ignoring other filters |

### 🎓 Performance & Training (6 measures — note: corrected count from 6 listed here in _Measures)

| Measure | DAX Logic | Business Purpose |
|---|---|---|
| `Avg_Performance_Rating` | `AVERAGE(Performance[Rating])` | Avg performance score |
| `High_Performer_%` | `DIVIDE([High_Performers_Count],[Active_Headcount])` | % of workforce rated high |
| `High_Performers_Count` | `CALCULATE(COUNTROWS(...), Rating="High")` | Absolute high-performer count |
| `Avg_Training_Cost` | `DIVIDE([Total_Training_Cost],[Active_Headcount])` | Avg spend per employee |
| `Total_Training_Cost` | `SUM(Training[Training Cost])` | Org-wide training investment |
| `Training_Cost_Rank` | `RANKX(ALL(Dept),[Total_Training_Cost],,DESC)` | Dept rank by training spend |

> 📝 *All DAX expressions are stored in the `_Measures` table inside the `.pbix` file and can be inspected in **Power BI Desktop → Data View → `_Measures` table**.*

---

## 🛠️ Technical Implementation

### ⚙️ Power Query (M) Transformations

| Transformation | Table Affected | Detail |
|---|---|---|
| Data type standardization | All tables | Ensured consistent int/text/date types across all 6 tables |
| Career Level Band derivation | `EmployeeMaster` | Mapped tenure + level to Beginner / Intermediate / Experienced |
| Salary Band grouping | `EmployeeMaster` | Created A/B/C/D salary bands for compensation analysis |
| YoY comparison columns | `Recruitment` | Added year columns to enable SAMEPERIODLASTYEAR comparisons |
| Department Type clean-up | `EmployeeMaster` | Standardized to 6 categories: Production, IT/IS, Sales, Software Engineering, Admin Offices, Executive Office |
| Employment status flag | `EmployeeMaster` | Derived Active vs. Terminated flag from raw data |
| Training outcome parsing | `Training` | Cleaned and categorized training outcomes for performance analysis |

### 🎨 Design & UX Choices

| Design Element | Choice | Reason |
|---|---|---|
| **Color theme** | Navy blue `#2C3E70` + Gold `#FFD700` | Corporate, authoritative, high-contrast readable |
| **Navigation** | Custom icon-based left sidebar | Persistent navigation without breaking filter context |
| **KPI layout** | Card visuals in top row | Instant headline metrics before chart detail |
| **Chart types** | Bar, line/area, donut, matrix | Matched to data type — ranking → bar, trend → line, composition → donut |
| **Cross-page filters** | Department + Career Band + Year | Enables consistent drill-down across all 3 pages |
| **YoY comparison** | Built into visuals via DAX | Avoids manual calculation — dynamic with any year selection |
| **Sidebar icons** | Custom PNG icons per page | Professional look; replaces default Power BI tab navigation |

### 📐 Data Relationships

```
EmployeeMaster[EmpID]     ──1:M──  Training[Employee ID]
EmployeeMaster[EmpID]     ──1:M──  EngagementSurvey[Employee ID]
EmployeeMaster[EmpID]     ──1:M──  Performance[Employee ID]
EmployeeMaster[EmpID]     ──1:M──  Recruitment[Applicant ID]
Dimdate[Date]             ──1:M──  Training[Training Date]
Dimdate[Date]             ──1:M──  Recruitment[Application Date]
```

---

## 💡 Key Insights Uncovered

### 🧭 Workforce Overview

| Finding | Detail | Implication |
|---|---|---|
| 🏭 Production dominates headcount | **17.0K active employees** — 5× larger than IT/IS (3.5K) | Resource concentration risk; high dependency on one department |
| 🚺 Slight female majority | **55.83%** female across all employees | Positive gender diversity signal — above average for large orgs |
| 📊 Experienced-heavy workforce | **48.02%** in "Experienced" career band | Strong talent maturity; succession planning critical |
| 🕐 Moderate average tenure | **5.42 years** avg tenure | Mid-range — neither a retention crisis nor a stagnation risk |
| 💸 Large training investment | **$2.79 Cr** total | Signals commitment to L&D; Production dominates spend |

### 📉 Attrition Analysis

| Finding | Detail | Implication |
|---|---|---|
| 🚨 Admin Offices attrition crisis | **27.19%** attrition — nearly **3× IT/IS (9.53%)** | Priority retention intervention needed in Admin |
| 📈 Hiring ramp is strong | **+134.18% YoY** new hires | Company is scaling fast — onboarding readiness is key |
| 📅 Hiring is back-loaded | Peaks in **September (9.1K)** and **March (9.9K)** | Seasonal hiring patterns — HR must plan capacity in Q1 and Q3 |
| 🚪 1,050 exits YTD | YTD attrition rate of **21.67%** | High termination volume — exit interview data review recommended |

### 💰 Compensation & Training

| Finding | Detail | Implication |
|---|---|---|
| ⚖️ Perfectly balanced pay distribution | **50/50** above/below average salary | Fair pay spread — no systemic skew toward over/underpaying |
| 🏭 Production consumes most training | **$19M** training spend — dwarfs all other departments | Justifiable given headcount; ROI per-employee may be lower than smaller depts |
| 📊 "Meets Expectations" dominates | **12,605 of 24,554** rated "Meets Expectations" | Normal distribution — most workforce is performing to standard |
| 🎓 Highest per-employee training in smaller depts | IT/IS and Software Eng likely highest per-capita | Potential for targeted upskilling ROI tracking |

---

## 🚀 How to Use

### Step 1 — Clone the Repository
```bash
git clone https://github.com/HarshalVora86/HR_Workforce_Analytics_Dashboard_Power_BI.git
cd HR_Workforce_Analytics_Dashboard_Power_BI
```

### Step 2 — Open in Power BI Desktop
```
1. Download Power BI Desktop (free) → https://powerbi.microsoft.com/desktop
2. File → Open → HR_Workforce_Analytics_Dashboard.pbix
3. If prompted about data source credentials, click "Edit Credentials" and set to Anonymous / local file
```

### Step 3 — Explore the Data Model
```
1. Click "Model view" (left sidebar icon) to see all 6 tables and relationships
2. Open "Data view" and select the _Measures table to inspect all 29 DAX formulas
3. Hover over any measure name → "Go to definition" to see the full DAX expression
```

### Step 4 — Navigate the Dashboard
```
Page 1 — Workforce Overview   → Use sidebar icon ⚙️
Page 2 — Attrition Analysis   → Use sidebar icon 🔁
Page 3 — Compensation         → Use sidebar icon 💵

Use the Department / Career Band / Year slicers to drill into any segment.
All three pages stay in sync with the same filter selections.
```

### Step 5 — Customize for Your Data
```
1. Home → Transform Data → Power Query Editor
2. Update the data source paths under each table's "Source" step
3. Click "Close & Apply" — all DAX measures recalculate automatically
```

---

## 🧰 Tools & Technologies

<p align="center">
  <img src="https://img.shields.io/badge/Power%20BI%20Desktop-F2C811?style=for-the-badge&logo=powerbi&logoColor=black" height="32"/>
  &nbsp;&nbsp;
  <img src="https://img.shields.io/badge/DAX-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white" height="32"/>
  &nbsp;&nbsp;
  <img src="https://img.shields.io/badge/Power%20Query%20M-217346?style=for-the-badge&logo=microsoft&logoColor=white" height="32"/>
  &nbsp;&nbsp;
  <img src="https://img.shields.io/badge/Star%20Schema%20Modeling-28A745?style=for-the-badge&logo=databricks&logoColor=white" height="32"/>
  &nbsp;&nbsp;
  <img src="https://img.shields.io/badge/People%20Analytics-2C3E70?style=for-the-badge&logo=googlescholar&logoColor=white" height="32"/>
</p>

| Category | Technology | Usage in This Project |
|---|---|---|
| **Reporting** | Power BI Desktop | All 3 dashboard pages, KPI cards, charts, navigation |
| **Analytics** | DAX | 29 custom measures — headcount, attrition, salary, training |
| **Data Prep** | Power Query (M) | Type standardization, band derivation, status flags, YoY columns |
| **Modeling** | Star Schema | 6-table relational model with EmployeeMaster as central hub |
| **Time Intel** | Dimdate + DAX | YTD, YoY, SAMEPERIODLASTYEAR across hiring & training trends |
| **Design** | Power BI Themes + Custom PNGs | Navy/gold palette, icon sidebar, card formatting |

---

## 📁 Repository Structure

```
HR_Workforce_Analytics_Dashboard_Power_BI/
│
├── 📊 HR_Workforce_Analytics_Dashboard.pbix   ← Main Power BI report file
│
├── 📁 Screenshots/
│   ├── Page1.png          ← Workforce Overview screenshot
│   ├── Page2.png          ← Attrition Analysis screenshot
│   ├── Page3.png          ← Compensation & Training screenshot
│   └── ModelView.png      ← Data model relationship diagram
│
└── 📄 README.md           ← This file
```

---

## 👨‍💻 About the Author

<p align="center">
  <strong>dhruv prajapati</strong><br/>
</p>

<p align="center">
  <a href="https://github.com/HarshalVora86">
    <img src="https://img.shields.io/badge/GitHub-HarshalVora86-181717?style=for-the-badge&logo=github&logoColor=white"/>
  </a>
  &nbsp;&nbsp;
  <a href="https://www.linkedin.com/in/harshal-vora-344601251">
    <img src="https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=for-the-badge&logo=linkedin&logoColor=white"/>
  </a>
</p>

> 🤝 *Feel free to fork this repository, raise issues, or connect on LinkedIn for collaboration on analytics and Power BI projects.*

---

<p align="center">
  <img src="https://img.shields.io/github/stars/HarshalVora86/HR_Workforce_Analytics_Dashboard_Power_BI?style=social"/>
  &nbsp;
  <img src="https://img.shields.io/github/forks/HarshalVora86/HR_Workforce_Analytics_Dashboard_Power_BI?style=social"/>
  &nbsp;
  <img src="https://img.shields.io/github/watchers/HarshalVora86/HR_Workforce_Analytics_Dashboard_Power_BI?style=social"/>
</p>

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=2,12,19,24,30&height=120&section=footer&fontColor=white"/>
</p>
