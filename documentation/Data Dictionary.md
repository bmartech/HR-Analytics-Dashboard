# 📚 Data Dictionary

## Overview

This document describes the fields used in the HR Analytics Dashboard. It serves as a reference for understanding the dataset, data types, and how each field contributes to the dashboard.

---

## Dataset Information

| Property | Value |
|----------|-------|
| Dataset | IBM HR Analytics Employee Attrition |
| Total Records | 1,470 |
| Purpose | HR Workforce & Attrition Analysis |

---

# Employee Information

| Column | Data Type | Description | Used In |
|---------|-----------|-------------|---------|
| EmployeeNumber | Whole Number | Unique employee identifier | Data Model |
| Age | Whole Number | Employee age | KPIs, Age Band |
| Gender | Text | Employee gender | Slicers, Charts |
| MaritalStatus | Text | Employee marital status | Attrition Analysis |
| Education | Whole Number | Education level (1–5) | Analysis |
| EducationField | Text | Field of study | Workforce & Attrition |
| Department | Text | Employee department | All Pages |
| JobRole | Text | Employee job role | All Pages |
| JobLevel | Whole Number | Employee seniority level | Workforce Analysis |

---

# Employment Information

| Column | Data Type | Description | Used In |
|---------|-----------|-------------|---------|
| Attrition | Text | Indicates whether an employee left the organization | All Pages |
| BusinessTravel | Text | Employee travel frequency | Workforce Analysis |
| OverTime | Text | Indicates overtime status | Attrition Analysis |
| MonthlyIncome | Currency | Employee monthly salary | KPIs |
| PerformanceRating | Whole Number | Performance evaluation score | Workforce Analysis |
| JobSatisfaction | Whole Number | Job satisfaction rating | Workforce Analysis |
| WorkLifeBalance | Whole Number | Work-life balance rating | Workforce Analysis |
| YearsAtCompany | Whole Number | Years employed with the organization | KPIs (if used) |

---

# Calculated Columns

| Column | Purpose |
|---------|---------|
| Age Band | Groups employees into business-friendly age categories |
| Age Band Sort | Ensures logical sorting of age bands |
| WorkLifeBalance Label | Converts numeric ratings into descriptive labels |
| WorkLifeBalance Sort | Maintains logical order for work-life balance categories |

---

# DAX Measures

| Measure | Purpose |
|----------|---------|
| Total Employees | Counts all employees |
| Current Employees | Calculates active employees |
| Employees Left | Counts employees with Attrition = Yes |
| Attrition Rate | Calculates the percentage of employees who left |
| Average Age | Calculates average employee age |
| Average Monthly Income | Calculates average employee income |
| Average Job Satisfaction | Calculates average satisfaction score |
| Average Performance Rating | Calculates average performance score |
| Average Age (Employees Left) | Average age of employees who left |
| Average Monthly Income (Employees Left) | Average income of employees who left |

---

# Dashboard Usage

The fields above support:

- Executive reporting
- Workforce demographics
- Employee segmentation
- Attrition analysis
- Interactive filtering
- KPI reporting
- Business storytelling

---

# Notes

- Calculated columns were used for categorization and sorting.
- DAX measures were used for dynamic calculations and KPI reporting.
- Interactive slicers filter all dashboard pages simultaneously, providing a consistent analytical experience.