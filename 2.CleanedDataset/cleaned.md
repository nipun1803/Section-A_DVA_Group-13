# Data Cleaning & Preparation Report

## Overview
The raw dataset (`AI_Productivity_Features_Raw_Dataset .csv`) underwent a rigorous cleaning process to transform **5,600 raw records** into a production-ready analytical dataset. The process focused on handling missing values, standardizing text formats, and verifying numeric integrity to ensure reliable KPI calculation.

## 1. Missing Values Handling

### Challenge
Several columns contained blank or missing values, particularly in key numeric fields:
- `AI Tool Usage Hours Per Week`
- `Tasks Automated Percent`
- `Burnout Risk Score`
- `Work-Life Balance Score`

### Methodology
To maintain data distribution and avoid introducing bias through row deletion:
- **Numeric Fields:** Missing values were imputed using the **median** of the respective column. Determining the median is robust against outliers compared to the mean.
- **Categorical Fields:** Blank entries were replaced with a placeholder value **"Others"** to ensure consistent grouping in pivot tables and prevent data loss during segmentation.

## 2. Outlier Treatment

### Statistical Review
Extreme values were reviewed using basic statistical checks (min/max/quartiles) and column sorting.
- **Finding:** No unrealistic or physically impossible values (e.g., negative hours, >168 hours/week) were found in key numerical fields.
- **Decision:** Since the dataset represents varied employee behavior, extreme values were **retained** as they likely represent genuine high-performance or high-risk cases (e.g., "Toxic High Performers").

## 3. Transformations & Standardization

### Text Normalization
Text columns exhibited inconsistent casing (e.g., "HIGH", "high", "HiGh"), which would splinter pivot table groups.
- **Action:** Applied `TRIM()` to remove leading/trailing whitespace.
- **Action:** Applied `PROPER()` to capitalize the first letter of each word (e.g., "High", "Medium").
- **Impact:** Ensured uniform formatting for `Role`, `Employee Persona`, and `AI Leverage Classification` fields.

### Numeric Validation
- **Action:** Verified that all metric fields were stored as numbers rather than text strings to prevent errors during KPI calculation.

## 4. Feature Engineering

To move beyond raw operational metrics, **6 new KPI columns** were engineered directly in the dataset:

| New Column | Purpose |
| :--- | :--- |
| **Efficiency Leverage** | Measures output per unit of AI time. |
| **Deep Work Balance** | Calculates remaining focus time after structural overhead. |
| **Learning Zone** | Segments employees by learning intensity deviation. |
| **Employee Persona** | Behavioral clustering of performance vs. health. |
| **AI Leverage Classification** | Buckets AI usage into low/medium/high bands. |
| **Sustainability Rating** | Composite score penalizing burnout risk. |

## 5. Assumptions

- **Median Imputation:** It is assumed that median replacement preserves the realistic distribution of the population without significantly altering central tendency patterns.
- **Metric Validity:** Derived KPIs such as *Sustainability Rating* are treated as analytical models rather than clinically validated psychological scales.
