# KPI & Calculation Documentation

## KPI Formulas Reference

The following table documents the exact logic used to derive the project's strategic Key Performance Indicators (KPIs). All formulas reference **Row 2** as the first data row.

| KPI Name | Google Sheets Formula | Logic & Notes |
| :--- | :--- | :--- |
| **Efficiency Leverage** | `=IF(D2=0, 0, E2/D2)` | **Output per AI Hour.**<br>`D` = AI Usage Hours<br>`E` = Output |
| **Deep Work Balance** | `=(M2*5) - (I2+J2)` | **Net Focus Time.**<br>`M` = Focus Hrs/Day (x5 for weekly)<br>`I` = Meeting Hrs<br>`J` = Collab Hrs |
| **Sustainability Rating** | `=IF(O2=0, 0, (E2*(10-K2)) / (O2^2))` | **Composite Health Score.**<br>Penalizes high burnout heavily (O2^2).<br>`O` = Burnout Score<br>`K` = Error Rate |
| **Learning Zone** | `=IFS(L2<2,"Risk", L2<=5,"Stable", L2<=9,"Growth", L2>9,"Overload")` | **Learning Intensity Buckets.**<br>`L` = Learning Hours/Week |
| **AI Leverage** | `=IF(D2<5,"Low AI", IF(D2<=12,"Medium AI", "High AI"))` | **Usage Classification.**<br>`D` = AI Usage Hours/Week |
| **Employee Persona** | `=IF(AND(E2>35, OR(O2>8, K2>3)), "Toxic High Performer", IF(E2>35, "Star Performer", IF(OR(O2>8, K2>3), "Struggler", "Steady Worker")))` | **Behavioral Segmentation.**<br>Based on Output (E2), Burnout (O2), and Error Rate (K2). |

---

## Data Dictionary

### Raw Operational Fields
| Column Name | Data Type | Description |
| :--- | :--- | :--- |
| **AI Tool Usage Hours Per Week** | Numeric | Hours/week the employee uses AI tools. |
| **Tasks Automated Percent** | Numeric (%) | Percentage of tasks automated via AI. |
| **Manual Work Hours** | Numeric | Hours/week spent on non-automated tasks. |
| **Learning Time Hours Per Week** | Numeric | Hours/week dedicated to upskilling. |
| **Meeting Hours Per Week** | Numeric | Total weekly hours in meetings. |
| **Collaboration Hours** | Numeric | Hours spent working with colleagues. |
| **Error Rate Percent** | Numeric (%) | % of tasks containing errors/rework. |
| **Focus Hours Per Day** | Numeric | Average daily uninterrupted deep work. |
| **Burnout Risk Score** | Score (0–10) | Composite indicator of stress levels. |

### Derived KPI Fields
| Column Name | Data Type | Description |
| :--- | :--- | :--- |
| **Efficiency Leverage** | Numeric | Productivity efficiency ratio (Output / AI Input). |
| **Deep Work Balance** | Numeric | Calculated "safe" focus time remaining. |
| **Sustainability Rating** | Numeric | Long-term viability score (High = Sustainable). |
| **Learning Zone** | Categorical | Risk / Stable / Growth / Overload buckets. |
| **AI Leverage Classification** | Categorical | Low / Medium / High usage bands. |
| **Employee Persona** | Categorical | Performance/Health quadrant assignment. |

---

## Why Each KPI Matters

### 1. Efficiency Leverage
**Business Purpose:** Shows output generated per AI hour.
**Insight:** Helps distinguish "busy work" (high usage, low output) from genuine productivity gains.

### 2. Deep Work Balance
**Business Purpose:** Measures remaining focused work time.
**Insight:** A leading indicator of sustainability. Managers often have negative balances due to meeting overload.

### 3. Sustainability Rating
**Business Purpose:** Penalizes high burnout risk to assess long-term viability.
**Insight:** A high performer with a low sustainability rating is a flight risk, not an asset.

### 4. Employee Persona
**Business Purpose:** Identifies workforce segments.
**Insight:** Highlights "Toxic High Performers" — employees delivering results but at a cost to health or quality that creates hidden organizational liability.
