# 📊 AI at Work: Are We Gaining Efficiency but Losing Stability?

**An Analysis of AI Adoption, Productivity, Burnout & Long-Term Workforce Sustainability**

**Sector:** Artificial Intelligence & Human Capital Management

---

## Executive Summary

This capstone project analyzes whether increasing AI adoption in the workplace genuinely improves long-term productivity — or whether it quietly erodes human skills, deep thinking ability, and workforce stability. Through systematic data cleaning, KPI engineering, and visual analytics, we deliver insights that balance efficiency gains against sustainability risks.

**Core Achievement:** Analyzed 5,600 employee records across 21 variables, engineered 6 custom KPIs, and built a 3-view interactive dashboard — revealing that **Medium AI usage (5–12 hrs/week) maximizes sustainable output**, while excessive AI adoption increases burnout and error rates without proportional productivity gains.

---

## Business Context

### The Challenge

Organizations are rapidly adopting AI tools to boost productivity and reduce workload. However, raw adoption metrics mask critical risks:

- **Over-dependence on AI** may weaken independent thinking and problem-solving skills
- **Rising burnout** despite AI assistance — meetings, collaboration overload, and learning demands create hidden pressure
- **Quality degradation** — high AI users show higher error rates than moderate users
- **Toxic High Performers** — employees delivering strong output at unsustainable burnout levels represent a retention time bomb

### The Impact

Without structured sustainability analysis, organizations optimize for short-term output while accumulating long-term fragility — burnout-driven attrition, skill erosion, and concentrated risk in key roles.

### Our Solution

A complete data-to-insights pipeline that delivers:

- **Cleaned, validated dataset** with median-imputed missing values and standardized categories
- **6 purpose-built KPIs** measuring efficiency, focus quality, learning sustainability, and burnout risk
- **Interactive 3-view dashboard** revealing AI adoption patterns, performance-health trade-offs, and long-term risk
- **Actionable recommendations** for AI governance, meeting reduction, and workforce sustainability
- **Reproducible methodology** ensuring audit-ready data lineage

### Live Google Sheets Workbook

Access the complete working dataset, cleaning steps, pivot tables, and dashboard calculations directly:

👉 [Google Sheets Link](https://docs.google.com/spreadsheets/d/1LxDcVKBmP-0q5tzLr0PtYl5XSNiZD8AKb3fH8VQkD7Q/edit?usp=sharing)

This sheet contains:

- Cleaned dataset (5,600 records)
- KPI calculations & feature engineering
- Pivot tables (11 analyses)
- Dashboard source charts (3 views)
- Data cleaning audit trail

---

## Research Question

> *"As organizations adopt AI at scale, are they building sustainable capability — or accumulating hidden fragility?"*

This question guided our analytical framework and dashboard design, focusing on:

- **AI Effectiveness** → Who is using AI productively vs. just consuming hours?
- **Quality Impact** → Does higher AI usage reduce or increase errors?
- **Burnout & Health** → Which roles and personas face unsustainable stress?
- **Sustainability** → Can high performance be maintained without burning out?
- **Structural Drivers** → How do meetings, focus time, and learning load shape outcomes?

---

## Project Team — Group G-13

| Team Member | Role | Contribution |
|---|---|---|
| Nipun Patlori | Data Engineer | Data cleaning, KPI formula engineering, dashboard support |
| Ranvendra Pratap Singh | Presentation Lead | PPT creation, presentation delivery |
| Samarth Chaudhary | Lead Analyst | Dataset sourcing, lead analysis coordination |
| Keshav | KPI Designer | KPI analysis, report writing, documentation |
| Ashutosh Singh | Dashboard Developer | Dashboard design, visualization, chart creation |
| Aditya Raj | Report Writer | Dataset sourcing, report writing |

**Institute:** Rishihood University
**Faculty / Program:** Aayushi Vashishth
**Submission Date:** February 2026

---

## 📂 Dataset Specification

### Source Information

| Attribute | Details |
|---|---|
| **Provider** | Kaggle Open Datasets |
| **Dataset Name** | AI Productivity Tools and Feature Impact Dataset |
| **URL** | [kaggle.com/datasets/ashyou09/ai-productivity-tools-and-feature-impact-dataset](https://www.kaggle.com/datasets/ashyou09/ai-productivity-tools-and-feature-impact-dataset) |
| **Access** | Publicly available, no registration required via Kaggle API |

### Technical Profile

| Attribute | Value |
|---|---|
| **Records** | 5,600 employee records |
| **Columns** | 21 fields (15 raw + 6 derived KPIs) |
| **File Format** | CSV (UTF-8) |
| **Data Type** | Cross-sectional employee survey |
| **Domain** | AI & Workforce Productivity |
| **Primary Metrics** | AI Usage, Automation %, Burnout Risk, Efficiency Leverage, Sustainability Rating |
| **Intended Usage** | KPI dashboards, persona segmentation, sustainability analytics |

### Schema Definition

| Column | Data Type | Description | Example Values |
|---|---|---|---|
| Employee Id | String (UUID) | Unique employee identifier | `fab56130-fefc-47d6-ae7e-13e0eaa984c1` |
| Role | Categorical | Employee job function | Analyst, Designer, Developer, Manager, Marketer, Writer |
| Years of Experience | Numeric (Integer) | Professional experience in years | 1, 8, 14, 20 |
| AI Tool Usage Hours Per Week | Numeric | Hours per week using AI tools | 0.0, 7.5, 15.9, 24.9 |
| Tasks Automated Percent | Numeric (%) | Percentage of tasks automated via AI | 0.7, 28.0, 61.2 |
| Manual Work Hours | Numeric | Weekly hours on non-automated tasks | 10.0, 24.2, 42.8 |
| Error Rate Percent | Numeric (%) | Percentage of tasks with errors | 0.10, 2.70, 9.60 |
| Task Complexity | Categorical | Difficulty level of assigned tasks | Low, Medium, High |
| Meeting Hours Per Week | Numeric | Total weekly meeting hours | 1.0, 8.5, 22.5 |
| Collaboration Hours Per Week | Numeric | Weekly collaborative work hours | 2.60, 9.50, 18.00 |
| Focus Hours Per Day | Numeric | Average daily uninterrupted deep work hours | 0.10, 2.84, 5.76 |
| Work-Life Balance Score | Score (0–10) | Self-reported work-life balance indicator | 1, 5, 10 |
| Learning Time Hours Per Week | Numeric | Weekly hours for learning/upskilling | 1.00, 5.40, 9.80 |
| Burnout Risk Score | Score (0–10) | Composite burnout risk indicator | 1.00, 5.82, 10.00 |
| Deadline Pressure Level | Categorical | Perceived deadline pressure | Low, Medium, High |
| Efficiency Leverage | Derived (Numeric) | Output per AI usage hour | 0.00, 3.40, 27.15 |
| Deep Work Balance | Derived (Numeric) | Remaining focus hours after meetings & collaboration | -25.90, 8.80, 28.60 |
| Learning Zone | Derived (Categorical) | Learning intensity category | Risk, Stable, Growth, Overload |
| Employee Persona | Derived (Categorical) | Behavioral performance classification | Star Performer, Steady Worker, Struggler, Toxic High Performer |
| Sustainability Rating | Derived (Numeric) | Composite sustainability score penalizing burnout | 0.00, 30.96, 542.88 |
| AI Leverage | Derived (Categorical) | AI usage intensity classification | Low AI, Medium AI, High AI |
| Experience Range | Derived (Categorical) | Experience band in 4-year buckets | 0–4, 4–8, 8–12, 12–16, 16–20 |

### Sample Data (Cleaned Dataset)

| Employee Id | Role | Exp | AI Hrs/Wk | Tasks Auto % | Manual Hrs | Error % | Complexity | Meet Hrs | Collab Hrs | Focus Hrs/Day | WLB | Learn Hrs | Burnout | Pressure | Eff. Leverage | Deep Work | Learn Zone | Persona | Sustainability | AI Leverage | Exp Range |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| `fab56130...` | Manager | 18 | 7.5 | 7.1 | 36.5 | 0.40 | Medium | 13.5 | 11.40 | 3.80 | 8.00 | 3.30 | 10.00 | 0.95 | -8.40 | Risk | Struggler | 9.47 | High | 16-20 | Medium AI |
| `7f63c041...` | Designer | 5 | 4.5 | 10.7 | 22.6 | 2.70 | Low | 1.0 | 3.20 | 0.97 | 7.00 | 6.10 | 4.19 | 2.38 | 26.30 | Stable | Steady Worker | 56.75 | Low | 4-8 | Low AI |
| `2595a59e...` | Analyst | 7 | 7.4 | 28.0 | 25.7 | 2.10 | Low | 3.9 | 8.00 | 3.55 | 7.00 | 5.10 | 5.82 | 3.78 | 13.60 | Stable | Struggler | 65.01 | Moderate | 4-8 | Medium AI |
| `ab27df97...` | Analyst | 7 | 2.6 | 70.6 | 14.5 | 5.30 | High | 1.9 | 3.40 | 2.10 | 2.00 | 5.80 | 1.30 | 27.15 | 23.70 | Growth | Star Performer | 2,088.76 | Low | 4-8 | Low AI |
| `c4190510...` | Developer | 1 | 22.4 | 61.2 | 11.1 | 1.10 | Low | 10.1 | 12.40 | 5.32 | 4.00 | 4.20 | 7.07 | 2.73 | -1.50 | Risk | Toxic High Performer | 38.64 | Moderate | 0-4 | High AI |
| `d5319e5f...` | Marketer | 20 | 9.7 | 20.6 | 36.8 | 3.80 | High | 1.0 | 7.10 | 0.10 | 1.00 | 6.00 | 10.00 | 2.12 | 21.90 | Stable | Struggler | 21.24 | High | 16-20 | Medium AI |

---

## Data Engineering Pipeline

### Overview

The raw dataset underwent a structured multi-stage cleaning process to transform 5,600 records into analytics-ready data:

```
Raw Data → Text Normalization → Blank/Null Handling → Placeholder Removal →
Numeric Validation → Feature Engineering → Categorization → Analytics-Ready
```

### Key Transformations

| Stage | Objective | Method | Impact |
|---|---|---|---|
| Text Normalization | Standardize categorical fields | `TRIM()` + `PROPER()` for Role, Deadline Pressure Level | Eliminated mixed casing (`MArKEtEr`, `HIGH`, `ANalYst`) |
| Blank Handling (Numeric) | Fill missing values | `IF(ISBLANK(cell), MEDIAN(range), cell)` | 100% null elimination in numeric fields |
| Blank Handling (Categorical) | Fill missing categories | `IF(ISBLANK(A2), "Others", PROPER(TRIM(A2)))` | Zero blank categorical values |
| Numeric Validation | Ensure valid numbers | Format → Number, Data Validation | All numeric operations mathematically valid |
| Feature Engineering | Create analytical KPIs | Custom formulas (6 KPIs) | 6 derived columns added |
| Categorization | Bucket continuous variables | `IFS()`, nested `IF()`, `FLOOR()` | Learning zones, personas, AI tiers, experience ranges |

### Data Cleaning Summary Table

| Column Name | Issue Identified | Action Taken |
|---|---|---|
| **Role** | Mixed casing (`MArKEtEr`, `DEVELOPER`, `ANalYst`), blank values | Used `TRIM()` + `PROPER()` to standardize text and replaced blanks with `"Others"` using `IF()` |
| **AI Tool Usage Hours Per Week** | Blank values present | Replaced missing values with Median using `IF(blank, MEDIAN(), value)` |
| **Tasks Automated Percent** | Missing values | Filled blanks with Median to maintain distribution |
| **Collaboration Hours Per Week** | Blank or non-numeric values | Replaced invalid values with fallback median value `$S$6` |
| **Task Complexity Score** | Missing values | Filled blanks using Median |
| **Work Life Balance Score** | Missing values | Replaced blanks with Median |
| **Burnout Risk Score** | Missing values | Replaced blanks with Median |
| **Deadline Pressure Level** | Mixed casing (`high`, `HIGH`), blank cells | Standardized using `PROPER()` and replaced blanks with `"Others"` |
| **Employee Role (some rows)** | Completely blank role | Replaced blank with `"Others"` |
| **Derived — Efficiency Leverage** | Risk of divide-by-zero error | Used `IF(D2=0,0,E2/D2)` to prevent error |
| **Derived — Deep Work Balance** | Calculated field | Created formula `(Focus×5) - (Meeting + Collaboration)` |
| **Learning Zone** | Raw numeric learning hours | Categorized using `IFS()` into Risk / Stable / Growth / Overload |
| **Employee Persona** | Needed behavioral classification | Created nested `IF()` logic based on automation & burnout |
| **AI Leverage** | Raw numeric AI usage | Categorized into Low / Medium / High AI usage |
| **Experience Range** | Raw numeric years | Grouped into 4-year buckets using `FLOOR()` |
| **Sustainability Rating** | Composite metric | `=IF(O2=0,0,(E2*(10-K2))/(O2^2))` — penalizes high burnout |

### Quality Certification

| Quality Check | Status | Details |
|---|---|---|
| Null Values | ✅ Passed | 0 nulls in all critical fields |
| Text Standardization | ✅ Verified | All categorical values in Title Case |
| Numeric Constraints | ✅ Enforced | All scores and hours are valid numbers |
| Derived Column Accuracy | ✅ Validated | All 6 KPI formulas verified |
| Divide-by-Zero Protection | ✅ Enforced | Guard clauses in all division formulas |
| Categorization Logic | ✅ Clean | All zones, personas, and tiers assigned |

**Result:** Production-ready dataset with 5,600 validated records and 21 columns

📄 **Full Cleaning Methodology:** Complete data cleaning documentation available in repository

---

## KPI & Metric Framework

### KPI Definitions

| KPI | Definition | Formula | Business Purpose |
|---|---|---|---|
| **Efficiency Leverage** | Output generated per AI usage hour | `=IF(D2=0,0,E2/D2)` | Measures how effectively AI is being used. Higher values = stronger productivity per AI hour |
| **Deep Work Balance** | Remaining focused work hours after meetings & collaboration | `=(M2*5)-(I2+J2)` | Evaluates whether employees have sufficient uninterrupted time for critical thinking |
| **Learning Zone** | Categorizes learning intensity | `=IFS(G2<2,"Risk", G2<=5,"Stable", G2<=9,"Growth", G2>9,"Overload")` | Identifies whether employees are under-learning, balanced, growing, or overloaded |
| **Sustainability Rating** | Composite score combining productivity, error rate & burnout | `=IF(O2=0,0,(E2*(10-K2))/(O2^2))` | Penalizes high burnout to evaluate long-term stability rather than short-term output |
| **AI Leverage Classification** | Groups employees by AI usage intensity | `=IF(D2<5,"Low AI", IF(D2<=12,"Medium AI","High AI"))` | Enables comparison across different AI usage levels |
| **Employee Persona** | Behavioral performance classification | `=IF(AND(E2>35,OR(O2>8,K2>3)),"Toxic High Performer", IF(E2>35,"Star Performer", IF(OR(O2>8,K2>3),"Struggler","Steady Worker")))` | Identifies high-performing but high-risk employees |

### KPI-to-Objective Mapping

| Project Objective | Supporting KPI | How It Supports |
|---|---|---|
| Measure AI-driven productivity | Efficiency Leverage | Shows output generated per AI hour |
| Protect deep thinking ability | Deep Work Balance | Measures remaining focused work time |
| Ensure continuous skill growth | Learning Zone | Identifies balanced vs overloaded learning behavior |
| Monitor burnout & stability | Sustainability Rating | Penalizes high burnout risk to assess long-term viability |
| Compare AI intensity impact | AI Leverage Classification | Enables structured comparison across AI usage levels |
| Identify workforce risk segments | Employee Persona | Highlights high-performing but high-risk employees |

---

## Key Performance Indicators (KPIs)

Our dashboard tracks strategic metrics across **5 analytical dimensions:**

### AI Adoption & Efficiency
- **AI Tool Usage Hours by Role** — Average weekly AI hours across 6 roles
- **Tasks Automated Percent by Role** — Automation output per role
- **AI Leverage Distribution** — Low / Medium / High AI tier breakdown
- **Resource Consumption by Role** — Proportional AI budget usage

### Performance & Quality
- **Efficiency Leverage by Role** — Output per AI hour invested
- **Error Rate by AI Leverage Tier** — Quality impact of AI intensity
- **Top AI-Optimized Roles** — Automation vs. error rate trade-off
- **Tasks Automated vs. Error Rate** — Quality-adjusted automation analysis

### Burnout & Well-being
- **Burnout Risk Score by Role** — Role-level burnout comparison
- **Employee Persona Distribution** — Star / Steady / Struggler / Toxic breakdown
- **Performance vs. Health Scatter** — Efficiency Leverage vs. Burnout mapping
- **Sustainability Rating by Persona** — Long-term viability assessment

### Workforce Structure
- **Workforce Composition** — Headcount distribution across roles
- **AI Adoption vs. Manual Work** — AI displacement analysis by role
- **Daily Routine by Role** — Meeting / Focus / Learning time breakdown

### Experience & Learning
- **Error Rate by Experience Level** — Learning curve across 5 experience bands
- **Learning Zone Distribution** — Risk / Stable / Growth / Overload segmentation
- **Experience Range vs. AI Usage** — Adoption patterns by seniority

---

## Pivot Table Calculation Methodology

All analytics tables were generated using **Google Sheets Pivot Tables** with the following configurations:

| # | Output Analysis | Rows | Columns | Values & Aggregation |
|---|---|---|---|---|
| 1 | AI Adoption & Automation by Role | Role | — | AVG of AI Tool Usage Hours, AVG of Tasks Automated % |
| 2 | Role Performance Overview | Role | — | COUNT of Employee Id, AVG of AI Usage, AVG of Efficiency Leverage, AVG of Burnout Risk |
| 3 | AI Leverage Impact on Quality | AI Leverage | — | AVG of Error Rate % |
| 4 | Workforce Composition | Role | — | COUNTA of Employee Id (as %) |
| 5 | Performance vs. Health | Employee Persona | — | AVG of Efficiency Leverage, AVG of Burnout Risk Score |
| 6 | Resource Consumption | Role | — | AVG of AI Tool Usage Hours (as % of baseline) |
| 7 | Burnout Risk by Role | Role | — | AVG of Burnout Risk Score |
| 8 | Top AI-Optimized Roles | Role | — | AVG of Tasks Automated %, AVG of Error Rate % |
| 9 | AI Adoption vs. Manual Work | Role | — | AVG of AI Tool Usage Hours, AVG of Manual Work Hours |
| 10 | Experience Learning Curve | Experience Range | — | AVG of Error Rate % |
| 11 | Daily Routine by Role | Role | — | AVG of Meeting Hours, AVG of Focus Hours, AVG of Learning Time |

📄 **View Full Documentation:** Available in the Calculations section of the Google Sheets workbook

---

## Dashboard Design

### Dashboard Objective

The dashboard translates raw employee data into clear, decision-ready visual intelligence. It enables HR managers, department heads, and organizational leaders to monitor three interconnected dimensions simultaneously: **AI adoption efficiency**, **performance-health trade-offs**, and **long-term sustainability trends**.

### View Structure

| View | Title | Charts Included | Primary Audience |
|---|---|---|---|
| **View 1** | Summary / Hero Dashboard | KPI Tiles: Total Employees (5,600), Avg AI Usage (10.7 hrs/wk), Avg Tasks Automated (28.8%), Avg Burnout Risk (7.79/10) | C-Suite / Executives |
| **View 2** | AI Adoption & Productivity / Performance vs Health Risk | 5 interactive charts with Role and Persona slicers | HR Managers / Team Leads |
| **View 3** | Sustainability & Long-Term Risk | 4 charts: error trend, meetings vs focus, workforce composition, resource consumption | Operations / Strategy |

### View 1 — Summary / Hero Dashboard

Opens with the project title *"AI at Work: Are We Gaining Efficiency but Losing Stability?"* accompanied by four KPI scorecards: **Total Employees (5,600)**, **Average AI Usage (10.7 hrs/week)**, **Average Tasks Automated (28.8%)**, and **Average Burnout Risk Score (7.79/10)**. These tiles provide an immediate high-level snapshot that anchors all subsequent analysis.

### View 2 — AI Adoption & Productivity / Performance vs Health Risk

**Upper Section — AI Adoption & Productivity:**

- **AI Adoption & Automation Efficiency by Role:** Grouped bar chart — Developers and Writers show peak AI usage; Managers and Marketers show high automation efficiency relative to hours
- **AI Usage vs Manual Workload Analysis:** Grouped bar chart — high AI usage does not eliminate manual effort, particularly for Managers
- **AI Leverage vs Error Rate:** Bar chart by AI tier — High AI users record the highest average error rate (~2.42%), challenging the assumption that more AI = better quality

**Lower Section — Performance vs Health Risk:**

- **Performance vs Health Scatter:** Plots Efficiency Leverage against Burnout Risk by Employee Persona — Star Performers cluster at high efficiency/low burnout; Toxic High Performers show the dangerous high-output/high-burnout profile
- **Burnout Risk by Role:** Bar chart — Managers (8.24) and Developers (8.01) carry the highest risk

### View 3 — Sustainability & Long-Term Risk

- **Error Rate by Experience Level:** Line chart across 5 experience bands — declining trend from 2.40% (0–4 yrs) to 1.92% (16–20 yrs)
- **Meetings vs Focus vs Learning:** Stacked bar chart — Managers face 13.8 meeting hours crowding out 3.34 focus hours
- **Workforce Composition Donut:** Developers lead at 23.2%
- **Resource Consumption Pie:** Developers (27.0%) and Analysts (17.3%) consume the largest share

### Filters & Drilldowns

Interactive slicers: **Role**, **Employee Persona**, **AI Leverage**, **Burnout Risk by Role**, and **Experience Range**. Setting any slicer to "All" reverts to the full dataset.

---

## Insights Summary

| # | Insight Title | What It Means for the Organization |
|---|---|---|
| 1 | **AI Has a Productivity Ceiling** | Medium AI usage (5–12 hrs/week) maximizes output. Beyond this, productivity plateaus while burnout continues to climb. |
| 2 | **High AI Usage Increases Error Rates** | High AI users record the highest average error rate (≈2.42%) vs Medium (2.07%) and Low (1.90%). Automation without review introduces quality risk. |
| 3 | **Toxic High Performers Are a Hidden Liability** | A segment delivers strong output but operates at burnout levels above 8/10. High attrition risk with disproportionate organizational cost. |
| 4 | **Managers Face the Most Severe Workload Compression** | ≈13.8 meeting hours/week and only ≈3.34 focus hours/day — the most acute Deep Work deficit of any role. Direct driver of elevated burnout (8.24). |
| 5 | **Deep Work Balance Is a Leading Sustainability Indicator** | Roles with higher protected focus time consistently show stronger Sustainability Ratings. Focus hours are a structural input, not a luxury. |
| 6 | **Developers Combine High AI Use with Reasonable Sustainability** | Despite the highest AI usage, Developers maintain competitive sustainability — AI genuinely augments structured technical tasks. |
| 7 | **Learning Overload Reduces Sustainability** | Employees in the Overload zone (>9 hrs/week) show lower sustainability despite higher short-term productivity. Excessive learning demands are counterproductive. |
| 8 | **Experience Progressively Reduces Error Rate** | Error rates decline consistently from 2.40% (0–4 yrs) to 1.92% (16–20 yrs). Senior employees are better positioned to verify and correct AI-generated output. |
| 9 | **Burnout Is Role-Structural, Not Just AI-Driven** | Managers and Developers carry the highest burnout. For Managers, meeting load and collaboration demands are primary drivers; for Developers, AI usage volume plays a greater role. |
| 10 | **Resource Concentration Creates Dependency Risk** | Developers and Analysts together account for over 45% of organizational resource consumption. Talent attrition in these groups would create disproportionate operational disruption. |
| 11 | **Steady Workers Achieve the Most Stable Outcomes** | Employees with moderate AI usage, stable learning intensity, and controlled burnout show the most consistent sustainability ratings. |
| 12 | **Risk Is Concentrated Despite Broad Headcount Distribution** | While headcount spans six roles, performance instability concentrates in Managers (burnout-driven) and Developers (volume-driven). Interventions should prioritize these two segments. |

---

## Recommendations

### R1: Implement an AI Usage Governance Policy

| Attribute | Details |
|---|---|
| **Mapped Insight** | Insights 1 & 2 — Productivity ceiling and rising error rates at high AI usage |
| **Recommended Action** | Define a recommended AI usage band of 5–12 hours per week. Introduce quarterly AI usage audits tracking both output and error rate trends. Flag roles exceeding the threshold without proportional quality improvement. |
| **Business Impact** | High |
| **Feasibility** | Medium |

### R2: Embed Sustainability KPIs in Performance Reviews

| Attribute | Details |
|---|---|
| **Mapped Insight** | Insights 3 & 11 — Toxic High Performers and Steady Worker advantage |
| **Recommended Action** | Augment performance reviews with Sustainability Rating, burnout trajectory, and error trend metrics. Evaluate employees on how consistently and healthily they produce output — not volume alone. |
| **Business Impact** | High |
| **Feasibility** | High |

### R3: Protect Deep Work Time Across All Roles

| Attribute | Details |
|---|---|
| **Mapped Insight** | Insights 4 & 5 — Manager compression and Deep Work Balance as sustainability driver |
| **Recommended Action** | Mandate minimum 3 uninterrupted focus hours per day. Cap weekly recurring meetings at 8 hours organization-wide. Introduce "no-meeting" blocks of at least two mornings per week, particularly for Managers. |
| **Business Impact** | High |
| **Feasibility** | Medium |

### R4: Redesign Learning Programmes to Prevent Overload

| Attribute | Details |
|---|---|
| **Mapped Insight** | Insight 7 — Learning Overload reduces sustainability |
| **Recommended Action** | Target 3–5 hours per week of structured, spaced learning. Replace high-volume sprint training with modular, self-paced tracks. Measure effectiveness through skill application, not hours logged. |
| **Business Impact** | Medium |
| **Feasibility** | High |

### R5: Create Prompt Transparency and Knowledge Documentation

| Attribute | Details |
|---|---|
| **Mapped Insight** | Insight 3 — Toxic High Performers create knowledge silos via undocumented AI workflows |
| **Recommended Action** | Require that productivity gains achieved via AI be documented as organizational assets. Establish a shared company prompt library to prevent knowledge silos created by Toxic High Performers. |
| **Business Impact** | High |
| **Feasibility** | Medium |

### R6: Reduce Structural Burnout Drivers for Managers

| Attribute | Details |
|---|---|
| **Mapped Insight** | Insights 4, 9 & 12 — Role-specific burnout and resource concentration risk |
| **Recommended Action** | Conduct meeting audit for Manager roles targeting 20–30% reduction in weekly meeting load. Delegate routine decision gates to Steady Worker profiles to redistribute cognitive load. Monitor burnout scores quarterly. |
| **Business Impact** | High |
| **Feasibility** | Medium |

---

## Impact Estimation

| Category | Lever | Estimated Impact & Logic |
|---|---|---|
| **Cost Savings** | Reducing Toxic High Performer attrition | Replacing a skilled employee costs 50–200% of annual salary. If sustainable KPI frameworks prevent even 5% of burnout-driven exits across 5,600 employees (avg replacement cost 75% of $60K salary), the organization avoids approximately **$12.6M** in replacement costs annually. |
| **Quality Improvement** | Optimizing AI usage to the Medium AI band | If High AI employees reduce to Medium band, error rates projected to drop from 2.42% to ~2.07% — a **15% quality improvement**. Translates to fewer rework cycles and faster completion. |
| **Performance Improvement** | Protecting Deep Work time for Managers | Increasing focus hours for Managers by 1–2 hrs/day through meeting reduction is estimated to improve decision quality by **15–25%**, based on cognitive flow state research. |
| **Risk Reduction** | Implementing prompt transparency and AI documentation | Establishing a shared company prompt library reduces organizational dependency on individual employees' undocumented AI workflows, directly reducing continuity risk from Toxic High Performer attrition. |
| **Sustainability** | Redesigning learning programmes | Shifting employees from Overload (>9 hrs/week) to Stable/Growth (3–7 hrs/week) reduces stress-driven absenteeism. Spaced learning improves retention by **40–60%** over sprint formats. |

---

## Limitations

### Data Issues

- The dataset represents a **single-time snapshot** — trend analysis is cross-sectional, not longitudinal
- Behavioral variables (Burnout Risk Score, Work-Life Balance Score) are **model-generated estimates** and may carry subjectivity
- The dataset is **publicly available on Kaggle** and is synthetic or anonymized — direct extrapolation to specific organizations requires caution

### Assumption Risks

- Missing values were imputed using **column medians** — this preserves distribution shape but artificially reduces variance
- KPIs (Sustainability Rating, Deep Work Balance) are **analytical approximations** and have not been externally validated
- Employee Persona classification is **rule-based** — real behavior is more nuanced and continuous

### What Cannot Be Concluded

- **Causality cannot be established** — correlations do not prove that meetings cause burnout or AI causes errors
- **Future trajectories cannot be predicted** from single-period data — a low Sustainability Rating reflects a snapshot, not a forecast
- **Industry-level differences** cannot be controlled for — findings should not be applied uniformly across all contexts

---

## Future Scope

### Additional Analysis Possible with Current Data

- **Regression analysis** to quantify the relative contribution of each variable to the Sustainability Rating
- **K-Means clustering** to replace rule-based Persona classification with naturally occurring behavior groups
- **Network analysis** of collaboration patterns (if partner data available) to reveal single-point-of-failure risks

### New Data Required for Deeper Analysis

- **Time-series data** (6–12 months) to transform static description into dynamic forecasting
- **Organizational hierarchy data** to determine whether instability is role-driven or management-driven
- **Training completion records** to evaluate whether learning programmes produce measurable capability improvements
- **External benchmarking data** to contextualize findings against sector norms

---

## 🗂️ Repository Structure

```
Project Root
│
├── RawDataset/
│     └── dataset.csv
│
├── CleanedDataset/
│     ├── cleaned.csv
│     └── data_cleaning_report.md
│
├── Calculations_PivotTables/
│     ├── calculations.md
│     └── pivot_table_exports/
│
├── Dashboard/
│     └── dashboard.pdf
│
├── Presentation/
│     └── presentation.pdf
│
├── Documentation/
│     ├── ai_workforce_report.md
│     └── documentation.pdf
│
└── README.md
```

---

## Technology Stack

### Data Processing & Analysis

- **Google Sheets** — Primary tool for data cleaning, pivot tables, and KPI calculations
  - Data validation and conditional formatting
  - Pivot table aggregations for 11 analyses
  - Feature engineering (6 custom KPIs)

### Visualization & Dashboarding

- **Google Sheets Charts** — Interactive 3-view dashboard
  - Bar charts, scatter plots, line graphs, pie/donut charts
  - Color-coded KPI indicators
  - Dynamic filtering via slicers

### Version Control & Collaboration

- **GitHub** — Repository hosting and team collaboration

### Documentation

- **Markdown** — Technical documentation and README
- **PDF** — Final deliverables for stakeholder distribution

**Why Google Sheets?**

- ✅ **Accessibility** — No software installation required
- ✅ **Collaboration** — Real-time multi-user editing
- ✅ **Auditability** — Complete version history and change tracking
- ✅ **Business Alignment** — Familiar interface for non-technical stakeholders

---

## Academic Integrity & Reproducibility

### Methodology Transparency

Every transformation applied to the dataset is documented with:

- **Rationale** — Why the change was necessary
- **Method** — How the change was implemented (formula provided)
- **Impact** — What was improved
- **Validation** — How correctness was verified

### Reproducibility Guarantee

Running the cleaning pipeline on the raw dataset will produce identical results due to:

- Deterministic transformation rules
- No random sampling or stochastic processes
- Complete documentation of decision logic
- Median-based imputation (no randomized imputation)

### Audit Trail

- All cleaning steps tracked in `data_cleaning_report.md`
- Original raw data preserved and versioned
- KPI formulas visible in Google Sheets for verification
- Pivot table configurations documented

---

## Conclusion

This project set out to answer a deceptively simple question: **as organizations adopt AI at scale, are they building sustainable capability or accumulating hidden fragility?**

The analysis of 5,600 employee records across 15 variables, supported by 6 purpose-built KPIs and an interactive 3-view dashboard, delivers a clear and evidence-based answer.

### ✅ What's Working

- **AI integration delivers genuine productivity benefits** — but only within a balanced adoption range (5–12 hrs/week)
- **Medium AI users** consistently outperform in long-term sustainability metrics
- **Star Performers** prove that high output WITHOUT high burnout IS achievable
- **Experience reduces errors** — a clear, predictable 20.4% improvement over 20 years

### ⚠️ What Needs Attention

- **Managers are in crisis** — highest burnout (8.24), lowest AI adoption (6.5 hrs), most meetings (13.8 hrs/wk)
- **Higher AI usage correlates with higher error rates** (2.42% vs 1.90%) — quality safeguards needed
- **Toxic High Performers** are a retention time bomb — high output at unsustainable health cost
- **Learning Overload** (>9 hrs/week) reduces sustainability despite higher short-term productivity

### 🎯 The Bottom Line

> The most efficient organization is not the one that uses AI the most. It is the one that uses AI wisely enough to keep its people **capable, engaged, and sustainable** over the long term. This study provides the evidence and the roadmap to make that distinction actionable.

---

## Contribution Matrix

| Team Member | Dataset & Sourcing | Cleaning | KPI & Analysis | Dashboard | Report Writing | PPT | Overall Role |
|---|---|---|---|---|---|---|---|
| Samarth Chaudhary | ✓ | | | | ✓ | | Lead Analyst |
| Aditya Raj | ✓ | | | ✓ | | | Report Writer |
| Ashutosh Singh | ✓ | ✓ | | | | | Dashboard Developer |
| Nipun Patlori | | ✓ | ✓ | | | | Data Engineer |
| Keshav | | | ✓ | ✓ | | | KPI Designer |
| Ranvendra Pratap Singh | | | | | ✓ | ✓ | Presentation Lead |

**Declaration:** We confirm that the above contribution details are accurate and verifiable through version history and submitted project artifacts.

---

## Appendix

### Data Dictionary

| Column Name | Data Type | Description |
|---|---|---|
| AI Tool Usage Hours Per Week | Numeric | Hours per week using AI tools |
| Tasks Automated Percent | Numeric (%) | Percentage of tasks automated through AI |
| Manual Work Hours | Numeric | Weekly hours on non-automated manual tasks |
| Learning Time Hours Per Week | Numeric | Weekly hours for learning/upskilling |
| Meeting Hours Per Week | Numeric | Total weekly meeting hours |
| Collaboration Hours | Numeric | Weekly collaborative work hours |
| Error Rate Percent | Numeric (%) | Percentage of tasks with errors |
| Task Complexity | Categorical / Score | Difficulty level of assigned tasks |
| Focus Hours Per Day | Numeric | Average daily uninterrupted deep work hours |
| Work-Life Balance Score | Score (0–10) | Self-reported work-life balance indicator |
| Burnout Risk Score | Score (0–10) | Composite burnout risk indicator |
| Efficiency Leverage | Derived (Numeric) | `=IF(D2=0,0,E2/D2)` |
| Deep Work Balance | Derived (Numeric) | `=(M2*5)-(I2+J2)` |
| Sustainability Rating | Derived (Numeric) | `=IF(O2=0,0,(E2*(10-K2))/(O2^2))` |
| Learning Zone | Derived (Categorical) | Risk (<2 hrs), Stable (≤5), Growth (≤9), Overload (>9) |
| AI Leverage | Derived (Categorical) | Low AI (<5 hrs), Medium AI (≤12), High AI (>12) |
| Employee Persona | Derived (Categorical) | Star Performer, Toxic High Performer, Struggler, Steady Worker |
| Experience Range | Categorical | 0–4, 4–8, 8–12, 12–16, 16–20 |

### KPI Formulas Reference

| KPI | Formula | Notes |
|---|---|---|
| Efficiency Leverage | `=IF(D2=0,0,E2/D2)` | D = AI Usage Hours, E = Output |
| Deep Work Balance | `=(M2*5)-(I2+J2)` | M = Focus Hrs/Day, I = Meeting Hrs, J = Collab Hrs |
| Sustainability Rating | `=IF(O2=0,0,(E2*(10-K2))/(O2^2))` | O = Burnout Score, K = Error Rate |
| Learning Zone | `=IFS(L2<2,"Risk",L2<=5,"Stable",L2<=9,"Growth",TRUE,"Overload")` | L = Learning Hours/Week |
| AI Leverage | `=IF(D2<5,"Low AI",IF(D2<=12,"Medium AI","High AI"))` | D = AI Usage Hours/Week |
| Employee Persona | `=IF(AND(E2>35,OR(O2>8,K2>3)),"Toxic High Performer",IF(E2>35,"Star Performer",IF(OR(O2>8,K2>3),"Struggler","Steady Worker")))` | E = Output, O = Burnout, K = Error Rate |

### Dataset Source

- **Title:** AI Productivity Tools and Feature Impact Dataset
- **Source:** Kaggle — [https://www.kaggle.com/datasets/ashyou09/ai-productivity-tools-and-feature-impact-dataset](https://www.kaggle.com/datasets/ashyou09/ai-productivity-tools-and-feature-impact-dataset)
- **Access:** Publicly available

All data cleaning and KPI engineering were performed in Google Sheets as per capstone project requirements.

---

## License & Usage

**License Type:** Academic Use Only
**Institution:** Rishihood University
**Course:** Data Visualization & Analytics
**Academic Year:** 2025-2026

### Usage Terms

**Permitted:**
- Academic citation and reference
- Educational demonstrations
- Non-commercial analysis replication

**Prohibited:**
- Commercial use without permission
- Redistribution without attribution
- Modification without documentation

---

## Acknowledgments

### Data Source
- **Kaggle Community:** ashyou09 for providing the AI Productivity dataset
- **Open Data Initiative:** Supporting accessible data science education

### Tools & Platforms
- **Google Workspace:** For Sheets and collaboration features
- **GitHub:** For version control and project hosting
- **Markdown:** For documentation standardization

---

> **AI at Work: Are We Gaining Efficiency but Losing Stability?**
>
> Group G-13 | Rishihood University | February 2026

---

*"The most efficient organization is not the one that uses AI the most. It is the one that uses AI wisely enough to keep its people capable, engaged, and sustainable over the long term."*