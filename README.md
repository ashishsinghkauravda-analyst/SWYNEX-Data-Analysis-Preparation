# Subscription & Churn Analytics

## Project Overview

This project analyzes **subscription, revenue, customer churn, product usage, and support performance** using SQL.

The analysis is designed to answer important SaaS business questions such as:

* How many customers are active in the analyzed dataset?
* What is the total MRR and ARR?
* What is the overall customer churn rate?
* How does MRR change over time?
* Which industries and referral sources contribute the most customers?
* Which industries and subscription plans have higher churn?
* How does product feature usage relate to errors?
* How do support resolution time and customer satisfaction vary across features?

The project uses **PostgreSQL SQL** to transform raw SaaS data into analytical views that can be used for reporting and dashboarding.

---

## Business Objective

The main objective is to understand:

1. **Revenue Performance**

   * MRR
   * ARR
   * Monthly MRR trends

2. **Customer & Churn Analysis**

   * Total customers
   * Churned customers
   * Churn rate
   * Churn by industry
   * Churn by subscription plan

3. **Customer Segmentation**

   * Customers by referral source
   * Customers by industry

4. **Product Usage**

   * Feature usage
   * Feature errors
   * Product-level usage patterns

5. **Customer Support**

   * Average ticket resolution time
   * Average satisfaction score
   * Feature-level support metrics

---

## Tools & Technologies

* **PostgreSQL**
* SQL
* CTEs
* Aggregate Functions
* `CASE WHEN`
* `FILTER`
* `DATE_TRUNC`
* `JOIN`
* `GROUP BY`
* SQL Views

---

## Data Structure

The analysis uses the following cleaned tables:

* `clean.accounts`
* `clean.subscriptions`
* `clean.feature_usage`
* `clean.support_tickets`

### Key Data Relationships

```text
accounts
   │
   ├── subscriptions
   │       │
   │       └── feature_usage
   │
   └── support_tickets
```

---

# SQL Analysis

## 1. Executive Overview

The executive overview combines customer and subscription data to calculate key SaaS business metrics:

* Total Customers
* Total MRR
* Total ARR
* Churn Rate
* Average Seats

A SQL view named `clean.executive_overview` was created for these metrics.

### Key SQL Concepts

* `COUNT(DISTINCT)`
* `SUM()`
* `AVG()`
* `CASE WHEN`
* `JOIN`
* Percentage calculation

---

## 2. Monthly MRR Trend

The project analyzes monthly recurring revenue using `DATE_TRUNC()` to group subscription start dates by month.

The `clean.mrr_trend` view calculates:

* Month
* Total MRR

This allows the business to monitor how recurring revenue changes over time.

---

## 3. Customer Segmentation

Customers are segmented based on:

* Referral Source
* Industry

The `clean.customer_segments` view calculates the number of distinct customers for each referral-source and industry combination.

### Business Questions

* Which referral sources generate customers?
* Which industries have the largest customer base?
* How is the customer base distributed across acquisition sources and industries?

---

## 4. Churn Analysis

The project analyzes churn across:

* Industry
* Subscription Plan

The `clean.churn_analysis` view calculates:

* Churned Customers
* Total Customers
* Churn Rate

The analysis uses PostgreSQL's `FILTER` clause to calculate churned customers and combines account and subscription data through a JOIN.

### Churn Rate

```text
Churn Rate =
Churned Customers / Total Customers × 100
```

### Business Questions

* Which industries have higher churn?
* Which subscription plans experience more churn?
* Where should customer-retention analysis be focused?

---

## 5. Feature Usage & Support Analysis

The project combines product usage and customer support data.

### Feature Usage Metrics

* Total Feature Usage
* Average Errors

### Support Metrics

* Average Resolution Time
* Average Satisfaction Score

The analysis uses CTEs to first summarize feature usage and support-ticket information before combining the results at the feature level.

### SQL Concepts Used

* CTEs
* Multiple JOINs
* `SUM()`
* `AVG()`
* `GROUP BY`
* `LEFT JOIN`

---

# Key Analytical Areas

| Area         | Metrics / Analysis                 |
| ------------ | ---------------------------------- |
| Revenue      | MRR, ARR, Monthly MRR              |
| Customers    | Total Customers, Customer Segments |
| Churn        | Churned Customers, Churn Rate      |
| Segmentation | Industry, Referral Source          |
| Subscription | Plan Tier                          |
| Product      | Feature Usage, Errors              |
| Support      | Resolution Time, Satisfaction      |

---

# Business Insights This Analysis Can Support

The SQL analysis can help SaaS teams understand:

* Revenue performance and recurring-revenue trends
* Customer acquisition distribution
* Customer concentration by industry
* Churn patterns across industries and plans
* Product feature adoption and errors
* Customer support performance
* Potential areas for customer-retention investigation

---

# Project Structure

```text
Subscription-and-Churn-Analytics/
│
├── SQL/
│   └── subscription_churn_analysis.sql
│
├── README.md
│
└── Dashboard/
    └── ...
```

---

# SQL Skills Demonstrated

This project demonstrates practical SQL skills relevant to **Data Analyst and SaaS/Product Analyst roles**:

* Data aggregation
* Business KPI calculation
* Customer segmentation
* Churn analysis
* Revenue analysis
* Time-based analysis
* Multi-table JOINs
* CTEs
* Conditional aggregation
* PostgreSQL `FILTER`
* SQL Views
* SaaS metrics analysis

---

# Future Improvements

Possible extensions to the analysis include:

* Monthly/annual churn trends
* Customer retention analysis
* Cohort analysis
* Customer Lifetime Value (LTV)
* Net Revenue Retention (NRR)
* Gross Revenue Retention (GRR)
* Expansion and contraction MRR
* Plan-level revenue analysis
* Feature adoption vs. churn
* Support experience vs. churn

---

## Project Focus

**Role:** Data Analyst / SaaS Data Analyst
**Domain:** SaaS Analytics
**Primary Tool:** PostgreSQL
**Analysis Type:** Subscription, Revenue, Churn, Product & Support Analytics
