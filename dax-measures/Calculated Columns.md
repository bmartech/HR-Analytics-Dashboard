# 📋 Calculated Columns

This document contains the calculated columns created for the HR Analytics Dashboard.

Calculated columns were used to improve data readability, create meaningful business categories, and control the sorting of categorical values within Power BI visuals.

---

## 1. Age Band

### DAX

```DAX
Age Band =
SWITCH(
    TRUE(),
    'HR Analytics Data'[Age] < 25, "Under 25",
    'HR Analytics Data'[Age] <= 34, "25-34",
    'HR Analytics Data'[Age] <= 44, "35-44",
    'HR Analytics Data'[Age] <= 54, "45-54",
    "55+"
)
```

### Purpose

Groups employees into meaningful age categories for workforce and attrition analysis.

### Used In

- Executive Overview
- Attrition Analysis

---

## 2. Age Band Sort

### DAX

```DAX
Age Band Sort =
SWITCH(
    'HR Analytics Data'[Age Band],
    "Under 25", 1,
    "25-34", 2,
    "35-44", 3,
    "45-54", 4,
    "55+", 5
)
```

### Purpose

Ensures the Age Band categories appear in the correct business order instead of alphabetical order.

### Sort By

```
Age Band
↓
Sort by Column
↓
Age Band Sort
```

---

## 3. Work-Life Balance Label

### DAX

```DAX
WorkLifeBalance Label =
SWITCH(
    'HR Analytics Data'[WorkLifeBalance],
    1, "Poor",
    2, "Fair",
    3, "Good",
    4, "Excellent"
)
```

### Purpose

Converts numeric work-life balance ratings into descriptive labels that are easier for business users to understand.

### Used In

- Workforce Analysis

---

## 4. Work-Life Balance Sort

### DAX

```DAX
WorkLifeBalance Sort =
'HR Analytics Data'[WorkLifeBalance]
```

### Purpose

Maintains the logical display order:

1. Poor
2. Fair
3. Good
4. Excellent

instead of alphabetical sorting.

### Sort By

```
WorkLifeBalance Label
↓
Sort by Column
↓
WorkLifeBalance Sort
```

---

# Why Calculated Columns?

Calculated columns were used instead of measures because they create persistent values for every row in the dataset. This makes them ideal for:

- Categorizing continuous variables (e.g., Age → Age Band)
- Creating descriptive labels
- Defining custom sort orders
- Improving report readability

Measures, on the other hand, were used for dynamic calculations such as KPIs, averages, totals, and percentages.

---

# Dashboard Features Supported

These calculated columns enable:

- Workforce age segmentation
- Executive reporting
- Logical chart sorting
- Improved dashboard readability
- Better business storytelling