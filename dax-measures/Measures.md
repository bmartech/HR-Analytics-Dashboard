# 📐 DAX Measures

This document contains the key DAX measures used in the HR Analytics Dashboard.

---

## 1. Total Employees

```DAX
Total Employees =
COUNTROWS('HR Analytics Data')
```

**Purpose**

Returns the total number of employees in the dataset.

---

## 2. Employees Left

```DAX
Employees Left =
CALCULATE(
    COUNTROWS('HR Analytics Data'),
    'HR Analytics Data'[Attrition] = "Yes"
)
```

**Purpose**

Counts employees whose Attrition status is **Yes**.

---

## 3. Current Employees

```DAX
Current Employees =
[Total Employees] - [Employees Left]
```

**Purpose**

Calculates the number of active employees.

---

## 4. Attrition Rate

```DAX
Attrition Rate =
DIVIDE([Employees Left], [Total Employees], 0)
```

**Purpose**

Calculates the percentage of employees who left the organization.

---

## 5. Average Monthly Income

```DAX
Average Monthly Income =
AVERAGE('HR Analytics Data'[MonthlyIncome])
```

**Purpose**

Returns the average monthly salary of employees.

---

## 6. Average Age

```DAX
Average Age =
AVERAGE('HR Analytics Data'[Age])
```

**Purpose**

Calculates the average employee age.

---

## 7. Average Job Satisfaction

```DAX
Average Job Satisfaction =
AVERAGE('HR Analytics Data'[JobSatisfaction])
```

**Purpose**

Calculates the average employee job satisfaction score.

---

## 8. Average Performance Rating

```DAX
Average Performance Rating =
AVERAGE('HR Analytics Data'[PerformanceRating])
```

**Purpose**

Returns the average employee performance rating.

---

## 9. Average Age (Employees Left)

```DAX
Average Age (Attrition) =
CALCULATE(
    AVERAGE('HR Analytics Data'[Age]),
    'HR Analytics Data'[Attrition] = "Yes"
)
```

**Purpose**

Calculates the average age of employees who left.

---

## 10. Average Monthly Income (Employees Left)

```DAX
Avg Income (Attrition) =
CALCULATE(
    AVERAGE('HR Analytics Data'[MonthlyIncome]),
    'HR Analytics Data'[Attrition] = "Yes"
)
```

**Purpose**

Returns the average monthly income of employees who left.

---

## 11. Age Band

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

**Purpose**

Groups employees into age categories for analysis.

---

## 12. Work-Life Balance Label

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

**Purpose**

Converts numeric work-life balance ratings into descriptive labels.

---

## Dashboard Features Supported by These Measures

- Executive KPI Cards
- Workforce Analysis
- Attrition Analysis
- Interactive Slicers
- Dynamic Filtering
- Business Intelligence Reporting