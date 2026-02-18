# AI at Work: Are We Gaining Efficiency but Losing Stability?

### An Analysis of AI Adoption, Productivity, Burnout & Long-Term Workforce Sustainability | Data Visualization & Analytics Capstone Project

---

## Executive Summary

This capstone project investigates the critical intersection of Artificial Intelligence (AI) and human capital management. As organizations rapidly adopt AI to enhance productivity, our research examines the hidden risks associated with over-dependence, including the potential erosion of critical thinking skills and long-term workforce instability.

**Core Achievement:** Analyzed a workforce dataset of **5,600 employee records** across **24 variables**, developing a robust KPI framework (including a proprietary **Sustainability Rating**) to identify the "Post-AI" productivity ceiling and mitigate organizational fragility.

## Business & Research Context

### The Challenge
AI tools are increasingly integrated into daily workflows for writing, analysis, and decision-making. However, many organizations focus exclusively on short-term productivity gains without monitoring:
- **Over-dependence:** Erosion of independent thinking and problem-solving skills.
- **Structural Compression:** High meeting loads and continuous learning demands creating acute "Deep Work" deficits.
- **Burnout Risk:** The correlation between high AI adoption and elevated stress levels.

### Research Question
> "Are companies becoming more efficient today but weaker in the future? To what extent does increasing AI use improve productivity while impacting long-term employee stability?"

## Project Team – Group G-13

| Team Member | Role | GitHub Profile |
| :--- | :--- | :--- |
| **Samarth Chaudhary** | Project Lead & Lead Analyst | [Profile](https://github.com/Samarth-Chaudhary) |
| **Aditya Raj** | Data Engineer | [Profile](https://github.com/Aditya-Raj) |
| **Ashutosh Singh** | KPI Designer | [Profile](https://github.com/Ashutosh-Singh) |
| **Patlori Nipun** | Dashboard Developer | [Profile](https://github.com/Patlori-Nipun) |
| **Keshav** | Report Writer | [Profile](https://github.com/Keshav) |
| **Ranvendra Pratap Singh** | Presentation Lead | [Profile](https://github.com/Ranvendra) |

## 📂 Dataset Specification

### Source Information
- **Provider:** Kaggle Open Datasets
- **Dataset Name:** AI Productivity Tools and Feature Impact Dataset
- **URL:** [Kaggle Dataset Link](https://www.kaggle.com/datasets/ashyou09/ai-productivity-tools-and-feature-impact-dataset)

### Technical Profile
| Attribute | Details |
| :--- | :--- |
| **Records** | 5,600 employee records |
| **Columns** | 24 variables (including engineered KPIs) |
| **Temporal Scope** | Single-period snapshot |
| **Data Cleaning** | Handled missing values (median imputation) and text standardization |
| **Feature Engineering** | 6 custom KPIs for sustainability and performance modeling |

## Data Engineering Pipeline

The raw dataset underwent a systematic transformation to ensure analytical integrity:
1. **Raw Data Acquisition:** Sourcing via Kaggle API.
2. **Missing Value Handling:** Missing numerical values (e.g., AI usage hours) replaced with column medians; categorical blanks replaced with "Others".
3. **Text Standardization:** Applied `TRIM()` and `PROPER()` to ensure uniform casing across role and persona fields.
4. **Numeric Validation:** Verified data types for all metric fields to prevent calculation errors.
5. **Feature Engineering:** Implemented complex logical formulas in Google Sheets to generate strategic KPIs.

## Key Performance Indicators (KPIs)

Our framework measures efficiency, focus quality, and long-term risk:

- **Efficiency Leverage:** Output generated per AI usage hour.
- **Deep Work Balance:** Remaining focus hours after subtracting meetings and collaboration.
- **Learning Zone:** Categorizes learning intensity (Risk, Stable, Growth, Overload).
- **Sustainability Rating:** A composite score that penalizes high burnout risk to assess long-term viability.
- **AI Leverage Classification:** Segments users by AI intensity (Low, Medium, High).
- **Employee Persona:** Behavioral classification (e.g., Star Performer, Toxic High Performer).

## 🗂️ Repository Structure

```text
DVA_Capstone/
│
├── 1.RawDataset/
│     └── AI_Productivity_Features_Raw_Dataset .csv   # Original CSV
│
├── 2.CleanedDataset/
│     ├── Cleaned_Dataset.csv                         # Validated production-ready data
│     └── cleaned.md                                  # Detailed data cleaning report
│
├── 3.Calculations_PivotTables/
│     └── calculations.md                             # KPI formulas and logic
│
├── 4.Dashboard/                                      # Interactive visualization views
│
├── 5.Presentation/                                   # Stakeholder presentation deck
│
├── 6.Report/
│     └── DVA_ Report - Google Docs.pdf              # Comprehensive final analysis
│
└── README.md
```

## Technology Stack

- **Data Processing:** Google Sheets (Pivot tables, deterministic transformation rules)
- **Visualization:** Google Sheets Charts (KPI scorecards, scatter plots, donut charts)
- **Collaboration:** GitHub (Version control, documentation)
- **Documentation:** Markdown & PDF (Academic reporting)

## Strategic Insights & Recommendations

### Key Insights
1. **The Productivity Ceiling:** Maximum output is achieved at **5–12 hours/week** of AI usage. Beyond this, gains plateau and burnout risk climbs.
2. **The Quality Paradox:** "High AI" users exhibit higher average error rates (~2.1%) due to over-automation and reduced human verification.
3. **Toxic High Performers:** Individuals with high output but critical burnout levels (8/10+) represent a hidden organizational liability.

### Recommendations
- **R1: Implement AI Usage Governance:** Define a recommended usage band of 5–12 hours per week.
- **R2: Sustainability KPIs:** Integrate "Sustainability Rating" into standard performance reviews.
- **R3: Protect Deep Work:** Mandate a minimum of 3 uninterrupted focus hours per day.

## License & Citation

- **Institution:** Rishihood University
- **Course:** Data Visualization & Analytics Capstone Project
- **Academic Year:** 2025-2026

**Citation Format:**
*AI at Work: Are We Gaining Efficiency but Losing Stability?* Newton School of Technology Capstone Project, Group G-13. (2026).

---
*"The most efficient organization is not the one that uses AI the most. It is the one that uses AI wisely enough to keep its people capable, engaged, and sustainable over the long term."*
