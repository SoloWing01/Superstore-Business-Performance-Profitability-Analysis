# Superstore Business Performance & Profitability Analysis

## Overview

This project performs an exploratory and statistical analysis of the **Superstore dataset** to understand business performance and identify factors associated with profitability.

The analysis examines sales, profit, discounts, products, categories, customer segments, regions, and time-based performance.

The goal is to move beyond simple descriptive statistics and use statistical testing to determine whether observed differences and relationships are statistically significant.

---

## Business Problem

A business may generate high sales while still experiencing weak profitability due to discounts, product mix, regional differences, or loss-making products.

This project investigates:

> **What factors are associated with profitability in the Superstore business, and which products, categories, regions, discount levels, and time periods contribute most to or detract from overall business performance?**

---

## Objectives

* Understand the structure and quality of the dataset.
* Analyze Sales, Quantity, Discount, and Profit.
* Identify potential outliers.
* Calculate and analyze profit margins.
* Investigate the relationship between discount and profit.
* Compare profitability across product categories.
* Compare profitability across customer segments.
* Compare profitability across regions.
* Identify profitable and loss-making sub-categories.
* Identify products contributing to overall losses.
* Analyze monthly sales and profitability trends.
* Use statistical hypothesis testing to validate observed differences.
* Generate business-oriented insights and recommendations.

---

## Dataset

The Superstore dataset contains transaction-level information related to:

### Order Information

* Order ID
* Order Date
* Ship Date
* Ship Mode

### Customer Information

* Customer ID
* Customer Name
* Segment

### Geographic Information

* Country/Region
* State
* City
* Postal Code
* Region

### Product Information

* Category
* Sub-Category
* Product Name

### Business Metrics

* Sales
* Quantity
* Discount
* Profit

---

## Project Workflow

```text
Dataset
   ↓
Data Understanding
   ↓
Data Quality Checks
   ↓
Exploratory Data Analysis
   ↓
Descriptive Statistics
   ↓
Outlier Analysis
   ↓
Profit Margin Analysis
   ↓
Correlation Analysis
   ↓
Hypothesis Testing
   ↓
Category / Segment / Region Analysis
   ↓
Sub-Category & Product Analysis
   ↓
Time-Series Analysis
   ↓
Business Insights
   ↓
Recommendations
```

---

## Exploratory Data Analysis

The analysis examines the distribution and behavior of the major numerical variables:

* Sales
* Quantity
* Discount
* Profit

Descriptive statistics include:

* Mean
* Median
* Standard deviation
* Minimum
* Maximum
* Skewness
* Kurtosis

Visualizations are used to understand distributions, relationships, and differences between business groups.

---

## Outlier Analysis

Potential outliers are identified using the **Interquartile Range (IQR)** method.

$$
IQR = Q3 - Q1
$$

The boundaries are calculated as:

$$
Lower\ Bound = Q1 - 1.5(IQR)
$$

$$
Upper\ Bound = Q3 + 1.5(IQR)
$$

Extreme observations are investigated rather than automatically removed because they may represent genuine high-value transactions or significant losses.

---

## Profit Margin

Profit margin is calculated as:

$$
Profit\ Margin = \frac{Profit}{Sales} \times 100
$$

Profit margin is analyzed alongside total profit because high sales do not necessarily indicate strong profitability.

---

# Statistical Hypothesis Testing

A significance level of:

$$
\alpha = 0.05
$$

is used for the hypothesis tests.

## Hypothesis 1 — Discount and Profit

### Research Question

Is there a statistically significant association between discount and profit?

### Null Hypothesis ($H_0$)

There is no statistically significant association between discount and profit.

$$
H_0: \rho = 0
$$

### Alternative Hypothesis ($H_1$)

There is a statistically significant association between discount and profit.

$$
H_1: \rho \neq 0
$$

### Tests

* Pearson correlation
* Spearman correlation

> A statistically significant correlation indicates association, not causation.

---

## Hypothesis 2 — Profitability Across Categories

### Research Question

Does average profitability differ across Furniture, Office Supplies, and Technology?

### Null Hypothesis ($H_0$)

Mean profit is equal across all product categories.

$$
H_0:
\mu_{Furniture} = 8.96
\mu_{Office} = 20.56
\mu_{Technology} = 78.57
$$

### Alternative Hypothesis ($H_1$)

At least one category has a different mean profit.

### Tests

* One-way ANOVA
* Kruskal-Wallis test
* Tukey's HSD for appropriate post-hoc comparisons

---

## Hypothesis 3 — Profitability Across Customer Segments

### Research Question

Does profitability differ across Consumer, Corporate, and Home Office segments?

### Null Hypothesis ($H_0$)

Mean profitability is equal across all customer segments.

$$
H_0:
\mu_{Consumer} = 25.82
\mu_{Corporate} = 30.50
\mu_{HomeOffice} = 33.83
$$

### Alternative Hypothesis ($H_1$)

At least one customer segment has a different mean profitability.

### Tests

* One-way ANOVA
* Kruskal-Wallis test

---

## Hypothesis 4 — Profitability Across Regions

### Research Question

Does profitability differ across Central, East, South, and West?

### Null Hypothesis ($H_0$)

Mean profitability is equal across all regions.

$$
H_0:
\mu_{Central} = 17.07
\mu_{East} = 31.77
\mu_{South} = 28.85
\mu_{West} = 34.06
$$

### Alternative Hypothesis ($H_1$)

At least one region has a different mean profitability.

### Tests

* One-way ANOVA
* Kruskal-Wallis test
* Tukey's HSD for appropriate post-hoc comparisons

---

## Statistical Decision Rule

For each hypothesis test:

| Condition      | Decision             |
| -------------- | -------------------- |
| p-value < 0.05 | Reject $H_0$         |
| p-value ≥ 0.05 | Fail to reject $H_0$ |

A statistically significant result indicates evidence of a difference or association in the analyzed data. It does not, by itself, establish causation.

---

# Business Analysis

## Category Analysis

Profitability is compared across:

* Furniture
* Office Supplies
* Technology

The analysis considers total profit, average profit, transaction volume, discounts, and profit margin.

---

## Customer Segment Analysis

Customer profitability is evaluated across:

* Consumer
* Corporate
* Home Office

The analysis compares transaction volume and profitability metrics to identify differences between customer segments.

---

## Regional Analysis

Performance is analyzed across:

* Central
* East
* South
* West

Regional performance is evaluated using sales, profit, transaction volume, discount, and profit margin.

---

## Sub-Category Analysis

Sub-category analysis provides a more detailed view of product performance.

The analysis examines:

* Transaction volume
* Total sales
* Average sales
* Total profit
* Average profit
* Average discount
* Profit margin

This helps identify specific product groups that contribute strongly to profitability or losses.

---

## Loss-Making Product Analysis

The analysis identifies products and sub-categories contributing negatively to total profit.

Particular attention is given to loss-making areas such as:

* Tables
* Bookcases
* Supplies

A cumulative loss analysis is used to determine whether losses are concentrated among a relatively small number of products.

---

## Time-Series Analysis

Monthly business performance is analyzed using:

* Transaction volume
* Total sales
* Total profit
* Average sales
* Average profit
* Average discount
* Profit margin

The primary question is:

> **Do periods with higher sales also generate higher profitability?**

This helps distinguish sales growth from actual improvement in profitability.

---

# Key Insights

The analysis demonstrates several important characteristics of Superstore performance:

* Profitability varies substantially across products and sub-categories.
* High sales do not necessarily result in high profit.
* Discount levels are associated with profitability and should be analyzed carefully.
* Category, customer segment, and regional performance can differ considerably.
* Some products contribute disproportionately to overall losses.
* Monthly sales and profitability do not always move together.
* Product-level analysis can reveal patterns hidden by aggregate category-level metrics.

---

# Business Recommendations

Based on the analysis, the following areas can be considered for further investigation:

### 1. Review High-Discount Transactions

Analyze high-discount transactions alongside product margins to understand their effect on profitability.

### 2. Investigate Loss-Making Products

Review products with persistent negative profitability for potential pricing, discount, cost, or product-mix issues.

### 3. Monitor Sub-Category Performance

Track sub-category-level profitability rather than relying exclusively on overall category performance.

### 4. Analyze Regional Differences

Evaluate regional profitability together with product mix, transaction volume, discount levels, and profit margins.

### 5. Monitor Profitability Over Time

Track sales, profit, and profit margin together to distinguish revenue growth from sustainable profitability.

### 6. Use Statistical Evidence

Combine descriptive analysis with statistical testing when interpreting differences between business groups.

---

# Technologies Used

* **Python**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Seaborn**
* **SciPy**
* **Jupyter Notebook**
* **Statistical Hypothesis Testing**

---

# Statistical Methods

The project uses:

* Descriptive statistics
* IQR-based outlier detection
* Pearson correlation
* Spearman correlation
* One-way ANOVA
* Kruskal-Wallis test
* Tukey's HSD
* Group-level aggregation
* Time-series analysis
* Profit-margin analysis

---

# Project Structure

```text
Superstore-Business-Analysis/
│
├── superstore.ipynb
├── README.md
└── dataset/
    └── superstore.csv
```

---

# Conclusion

This project demonstrates how exploratory data analysis and statistical testing can be combined to understand business performance.

Rather than evaluating the business using sales alone, the analysis considers **profit, profit margin, discounting, product performance, customer segments, regions, and time trends**.

The resulting analysis provides a structured view of the factors associated with profitability and highlights areas that may require further business investigation.

---

## Author

**Vishal Shekhar**

Bachelor of Engineering — Computer Science & Engineering
