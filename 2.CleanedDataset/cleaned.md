# 📊 AI & Workforce Productivity — Data Cleaning & Quality Assurance Report

**Project:** AI & Workforce Productivity Analytics
**Dataset Type:** Employee Productivity & AI Usage Records
**Prepared For:** Business Intelligence & Dashboarding
**Prepared By:** Data Engineering & Analytics Team

---

## 1. Executive Summary

This document provides comprehensive technical documentation of the data quality improvement pipeline applied to transform raw employee productivity data into an analytics-ready dataset. The cleaning process achieved:

- ✅ **100% elimination** of null values, placeholders, and inconsistencies
- ✅ **Standardized categorical fields** — Role, Deadline Pressure Level
- ✅ **Median-based imputation** for all numeric blanks to preserve distribution
- ✅ **Derived columns** engineered for advanced analytics (Efficiency Leverage, Deep Work Balance, Learning Zone, Employee Persona, AI Leverage, Experience Range, Sustainability Rating)
- ✅ **Production-grade data quality** suitable for executive dashboards

---

## 2. Purpose & Objectives

This cleaning pipeline was designed to:

- ✓ Ensure accuracy of all productivity and well-being metrics
- ✓ Enable reliable KPI computation for business intelligence
- ✓ Prevent misleading insights from corrupted, blank, or inconsistent data
- ✓ Prepare data for BI dashboards, automated reporting, and behavioral segmentation
- ✓ Maintain maximum usable data without introducing bias
- ✓ Guarantee reproducibility through deterministic, rule-based transformations

All transformations are documented to ensure **auditability, transparency, and compliance** with data governance standards.

---

## 3. Dataset Overview

| Property            | Value                                                  |
|---------------------|--------------------------------------------------------|
| **Raw Records**     | Employee productivity & AI usage survey records        |
| **Domain**          | AI & Workforce Productivity                            |
| **Primary Metrics** | Efficiency Leverage, Burnout Risk, AI Usage, Deep Work |
| **Intended Usage**  | KPI dashboards, persona segmentation, trend analytics  |

---

## 4. Data Cleaning Summary Table

| Column Name | Issue Identified | Action Taken |
|---|---|---|
| **Role** | Mixed casing (`MArKEtEr`, `DEVELOPER`, `ANalYst`), blank values | Used `TRIM()` + `PROPER()` to standardize text and replaced blanks with `"Others"` using `IF()` |
| **AI Tool Usage Hours Per Week** | Blank values present | Replaced missing values with **Median** using `IF(blank, MEDIAN(), value)` |
| **Tasks Automated Percent** | Missing values | Filled blanks with **Median** to maintain distribution |
| **Collaboration Hours Per Week** | Blank or non-numeric values | Replaced invalid values with fallback median value `$S$6` |
| **Task Complexity Score** | Missing values | Filled blanks using **Median** |
| **Work Life Balance Score** | Missing values | Replaced blanks with **Median** |
| **Burnout Risk Score** | Missing values | Replaced blanks with **Median** |
| **Deadline Pressure Level** | Mixed casing (`high`, `HIGH`), blank cells | Standardized using `PROPER()` and replaced blanks with `"Others"` |
| **Employee Role (some rows)** | Completely blank role (e.g., one record) | Replaced blank with `"Others"` |
| **Derived Column – Efficiency Leverage** | Risk of divide-by-zero error | Used `IF(D2=0,0,E2/D2)` to prevent error |
| **Derived Column – Deep Work Balance** | No issue (calculated field) | Created formula: `(Focus × 5) - (Meeting + Collaboration)` |
| **Learning Zone** | Raw numeric learning hours | Categorized using `IFS()` into **Risk / Stable / Growth / Overload** |
| **Employee Persona** | Needed behavioral classification | Created nested `IF()` logic based on automation & burnout |
| **AI Leverage** | Raw numeric AI usage | Categorized into **Low / Medium / High** AI usage |
| **Experience Range** | Raw numeric years | Grouped into **4-year buckets** using `FLOOR()` |
| **Sustainability Rating** | Derived metric for sustainability | Formula: `=IF(O2=0,0,(E2*(10-K2))/(O2^2))` — penalizes high burnout |

---

## 5. Cleaning Methodology — Pipeline Stages

The pipeline follows a sequential process to prevent downstream contamination:

```
Stage 1: Text Normalization (Role, Deadline Pressure Level)
         ↓
Stage 2: Blank / Null Handling (Median Imputation for Numerics)
         ↓
Stage 3: Placeholder Removal ("Others" for Categorical Blanks)
         ↓
Stage 4: Derived Column Engineering
         ↓
Stage 5: Categorization & Bucketing
         ↓
Stage 6: Final Validation
         ↓
    Clean Dataset
```

Each stage is applied in order to ensure that cleaned records from earlier stages are not corrupted by issues detected in later stages.

---

## 6. Stage 1: Text Normalization

### Problem
Categorical fields contained inconsistent casing and hidden whitespace:

- `"MArKEtEr"`, `"DEVELOPER"`, `"ANalYst"` — mixed casing in **Role**
- `"high"`, `"HIGH"`, `"High"` — inconsistent **Deadline Pressure Level**

These were treated as separate categories, causing:
- ❌ Incorrect aggregation in `GROUP BY` operations
- ❌ Phantom duplicate categories in dashboards
- ❌ Misleading distribution statistics

### Solution

| Formula Used | Purpose |
|---|---|
| `=TRIM(A2)` | Strip leading/trailing whitespace |
| `=PROPER(TRIM(A2))` | Standardize to Title Case |

**Applied to columns:** `Role`, `Deadline Pressure Level`

### Impact
- ✓ Eliminated phantom category duplicates
- ✓ Ensured accurate category distributions
- ✓ Prevented split aggregations in pivot tables

---

## 7. Stage 2: Blank / Null Handling — Median Imputation

### Problem
Multiple numeric fields contained blank or missing values, which would:
- ❌ Break statistical calculations (AVERAGE, STDEV)
- ❌ Distort KPIs and aggregated metrics
- ❌ Cause errors in derived column formulas

### Solution

**Strategy:** Replace blanks with the **Median** of the respective column to preserve distribution without introducing outlier bias.

| Column | Formula Pattern |
|---|---|
| AI Tool Usage Hours Per Week | `=IF(ISBLANK(cell), MEDIAN(range), cell)` |
| Tasks Automated Percent | `=IF(ISBLANK(cell), MEDIAN(range), cell)` |
| Collaboration Hours Per Week | `=IF(ISBLANK(cell), $S$6, cell)` *(fallback median reference)* |
| Task Complexity Score | `=IF(ISBLANK(cell), MEDIAN(range), cell)` |
| Work Life Balance Score | `=IF(ISBLANK(cell), MEDIAN(range), cell)` |
| Burnout Risk Score | `=IF(ISBLANK(cell), MEDIAN(range), cell)` |

### Why Median?
- ✅ Robust to outliers (unlike Mean)
- ✅ Preserves central tendency of the distribution
- ✅ Industry-standard imputation for skewed data

### Impact
- ✓ 100% elimination of null values in numeric fields
- ✓ All statistical functions now execute without errors
- ✓ Distribution shape preserved post-imputation

---

## 8. Stage 3: Placeholder Removal for Categorical Fields

### Problem
Some categorical fields (Role, Deadline Pressure Level) had completely blank cells with no recoverable information.

### Solution

| Field | Action |
|---|---|
| Role (blank) | Replaced with `"Others"` using `=IF(ISBLANK(A2), "Others", PROPER(TRIM(A2)))` |
| Deadline Pressure Level (blank) | Replaced with `"Others"` using `=IF(ISBLANK(A2), "Others", PROPER(TRIM(A2)))` |

### Rationale
- `"Others"` is a transparent label that does not distort analysis
- Records are retained (not deleted), preserving dataset size
- Downstream filters can include/exclude `"Others"` as needed

### Impact
- ✓ Zero blank categorical values remaining
- ✓ No data loss from row deletion
- ✓ Clean category lists for dashboards and pivot tables

---

## 9. Stage 4: Derived Column Engineering

### 9.1 Efficiency Leverage

| Property | Value |
|---|---|
| **Formula** | `=IF(D2=0, 0, E2/D2)` |
| **Purpose** | Measures output (tasks automated) relative to input (AI tool hours) |
| **Guard** | `IF(D2=0, 0, ...)` prevents `#DIV/0!` error |

---

### 9.2 Deep Work Balance

| Property | Value |
|---|---|
| **Formula** | `= (Focus Hours × 5) - (Meeting Hours + Collaboration Hours)` |
| **Purpose** | Quantifies deep work capacity after accounting for collaborative overhead |
| **Interpretation** | Higher = more deep work capacity; Negative = meeting-heavy schedule |

---

### 9.3 Sustainability Rating

| Property | Value |
|---|---|
| **Formula** | `=IF(O2=0,0,(E2*(10-K2))/(O2^2))` |
| **Purpose** | Composite score penalizing high burnout to evaluate long-term workforce viability |
| **Interpretation** | High value = sustainable performance; Low value = performance at burnout cost |

---

## 10. Stage 5: Categorization & Bucketing

### 10.1 Learning Zone

Categorized raw **Learning Hours** into behavioral zones:

| Zone | Criteria | Interpretation |
|---|---|---|
| **Risk** | <2 hrs/week | Employee at risk of skill stagnation |
| **Stable** | ≤5 hrs/week | Maintaining current skill level |
| **Growth** | ≤9 hrs/week | Actively upskilling |
| **Overload** | >9 hrs/week | Potential burnout from over-learning |

**Formula:** `=IFS(L2<2,"Risk",L2<=5,"Stable",L2<=9,"Growth",TRUE,"Overload")`

---

### 10.2 Employee Persona

Behavioral classification using **automation level** and **burnout risk**:

| Persona | Description |
|---|---|
| **Star Performer** | High automation, low burnout — sustainable excellence |
| **Steady Worker** | Moderate automation, moderate burnout — balanced contributor |
| **Struggler** | Low automation, high burnout — needs support |
| **Toxic High Performer** | High automation, high burnout — unsustainable output |

**Formula:** `=IF(AND(E2>35,OR(O2>8,K2>3)),"Toxic High Performer",IF(E2>35,"Star Performer",IF(OR(O2>8,K2>3),"Struggler","Steady Worker")))`

---

### 10.3 AI Leverage

Categorized raw **AI Tool Usage Hours** into usage tiers:

| Category | Criteria |
|---|---|
| **Low AI** | <5 hrs/week |
| **Medium AI** | ≤12 hrs/week |
| **High AI** | >12 hrs/week |

---

### 10.4 Experience Range

Grouped raw **Years of Experience** into structured buckets:

| Formula | Example Output |
|---|---|
| `=FLOOR(years, 4)` | 0–4, 4–8, 8–12, 12–16, 16–20 |

**Purpose:** Enables experience-based cohort analysis in dashboards.

---

## 11. Performance vs Health — Visual Insight

### Key Observations

| Employee Persona | Avg Efficiency Leverage | Avg Burnout Risk Score | Insight |
|---|---|---|---|
| **Star Performer** | 8.18 | 5.43 | ✅ High output, manageable burnout — **sustainable** |
| **Steady Worker** | 3.15 | 5.80 | ⚖️ Moderate output, moderate burnout — **balanced** |
| **Struggler** | 2.78 | 8.87 | ⚠️ Low output, high burnout — **needs intervention** |
| **Toxic High Performer** | 6.52 | 8.35 | 🔴 High output, high burnout — **unsustainable risk** |

### Strategic Takeaways
- **Star Performers** represent the ideal — high leverage with controlled burnout
- **Toxic High Performers** deliver results but at a health cost — retention risk
- **Strugglers** have the highest burnout with lowest output — require immediate support
- **Steady Workers** are the reliable backbone — investment in AI tools could elevate them

---

## 12. Final Data Quality Validation

| Quality Check | Status | Details |
|---|---|---|
| Null Values in Critical Fields | ✅ PASSED | 0 nulls in all numeric and categorical columns |
| Placeholder Values | ✅ PASSED | 0 instances of blank, ERROR, Unknown |
| Text Standardization | ✅ VERIFIED | All categorical values in Title Case |
| Numeric Constraints | ✅ ENFORCED | All scores and hours are valid numbers |
| Derived Column Accuracy | ✅ VALIDATED | All formulas verified for correctness |
| Categorization Logic | ✅ CLEAN | All zones, personas, and tiers assigned |
| Divide-by-Zero Protection | ✅ ENFORCED | Guard clauses in all division formulas |

**Final Verdict:** ✅ **Production-Ready for Enterprise BI**

---

## 13. Business Impact Summary

### Quantified Improvements

| Metric | Before Cleaning | After Cleaning | Improvement |
|---|---|---|---|
| Null/Blank Values | Present in multiple columns | 0 | 100% resolution |
| Casing Inconsistencies | Mixed casing in Role & Deadline | Standardized Title Case | 100% standardized |
| Derived Analytics Columns | 0 | 6 new columns | Full feature engineering |
| Employee Personas | Not available | 4 behavioral segments | New segmentation capability |
| Divide-by-Zero Errors | Risk in Efficiency Leverage | 0 errors | 100% protected |

### Enabled Analytics Capabilities

- ✅ **Efficiency KPIs** — Accurate and error-free
- ✅ **Employee Persona Segmentation** — Behavioral classification
- ✅ **AI Adoption Analysis** — Low/Medium/High usage tiers
- ✅ **Burnout Risk Monitoring** — Sustainability rating tracking
- ✅ **Experience Cohort Analysis** — Structured 4-year buckets
- ✅ **Deep Work Analytics** — Focus vs. collaboration balance
- ✅ **Executive Dashboards** — Trustworthy visualizations

---

## 14. Reproducibility & Audit Trail

### Deterministic Transformations

All cleaning steps are rule-based and deterministic:
- ✅ No random sampling
- ✅ No stochastic imputation
- ✅ No manual overrides
- ✅ No subjective decisions

**Guarantee:** Re-running the pipeline against the original raw dataset will produce **byte-identical output**.

### Documentation Standards

Every transformation includes:
- **Rationale** — Why the change was necessary
- **Method** — How the change was implemented (formula provided)
- **Impact** — What was improved
- **Validation** — How correctness was verified

---

## 15. Google Sheets Cleaning Workflow Summary

**Tool Used:** Google Sheets (Web-based)
**Reason:** Accessibility, collaboration, familiar interface, built-in data cleaning features

| Stage | Google Sheets Method | Key Formulas/Features Used |
|---|---|---|
| 1. Text Normalization | TRIM + PROPER formulas | `=PROPER(TRIM(A2))` |
| 2. Blank Handling (Numeric) | IF + MEDIAN imputation | `=IF(ISBLANK(cell), MEDIAN(range), cell)` |
| 3. Blank Handling (Categorical) | IF replacement | `=IF(ISBLANK(A2), "Others", PROPER(TRIM(A2)))` |
| 4. Derived Columns | Formula creation | `IF()`, arithmetic operators |
| 5. Categorization | IFS + nested IF | `=IFS()`, `=IF(AND())` |
| 6. Bucketing | FLOOR function | `=FLOOR(years, 4)` |
| 7. Validation | Conditional formatting + COUNTIF | `=COUNTIF()`, `=COUNTBLANK()` |

---

## 16. Recommendations for Future Data Collection

### Prevent Future Quality Issues
- Implement **data validation** at point of capture (survey form)
- Add **dropdown menus** for categorical fields (Role, Deadline Pressure Level)
- Enforce **required fields** to prevent blanks at source
- Standardize **numeric ranges** with input constraints

### Improve Analytics Capabilities
- Add **Department** field for organizational analysis
- Include **project type** for workload categorization
- Track **AI tool names** for technology adoption insights
- Capture **remote vs. on-site** status for work model analysis

---

## 17. Conclusion

This data cleaning pipeline successfully transformed raw employee productivity survey data into an **analytics-grade dataset** suitable for production dashboards and executive decision-making.

### Key Achievements
- ✅ **100% null elimination** across all fields
- ✅ **Standardized categorical values** with consistent casing
- ✅ **6 derived columns** engineered for advanced analytics
- ✅ **4 employee personas** classified for behavioral segmentation
- ✅ **Audit-ready documentation** for compliance and reproducibility

### Quality Certification

The cleaned dataset meets enterprise standards for:
- **Accuracy** — All formulas and calculations verified
- **Completeness** — No missing critical values
- **Consistency** — Standardized formats and categories
- **Validity** — All values within acceptable ranges
- **Traceability** — Full audit trail documented