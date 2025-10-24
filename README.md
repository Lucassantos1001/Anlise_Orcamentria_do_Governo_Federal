# Analise Orçamentria do Governo Federal
College project for my database discipline. I used MongoDB and BI tools to analyze and extract strategic insights from 2014 Brazilian Federal Government budget data, focusing on expenditure efficiency and resource allocation. 

# 📊 Federal Government Budget Analysis (2014)

## ✨ Project Overview

This project is the result of a fictional data consultancy where we acted as **Data Consultants** for an internal control agency. Our goal was to dive into the expenditure data of the Brazilian Federal Government, leveraging the flexibility and aggregation power of **MongoDB (NoSQL)**, to extract valuable insights that could guide strategic decisions and enhance the oversight of public spending.

The analysis focused on the **2014** period, providing a detailed snapshot of how resources were planned, distributed, and actually executed by various federal ministries.

## 🎯 Business Problem

The Federal Government moves billions of reais annually. The central challenge is ensuring **efficiency** and **transparency** in the application of these resources. Budgetary data is often dispersed, and the lack of clear analysis prevents the identification of bottlenecks and opportunities for management improvement.

**Our Purpose:** To bring clarity to this complex scenario by answering strategic questions that impact the control agency's decision-making process.

## 🛠️ Technologies Used

| Category | Technology | Description |
| :--- | :--- | :--- |
| **Database** | **MongoDB** | A document-oriented NoSQL database, chosen for its flexibility and ability to handle large volumes of data scalably. |
| **Data Analysis** | **MongoDB Aggregation Framework** | Used to perform data engineering, cleaning, transformations, and complex analyses, such as percentage calculations and annual groupings. |
| **Visualization** | **Business Intelligence (BI)** | A BI tool (not specified in the report, but essential for the final stage) used to create *dashboards* and charts that humanize the data and communicate *insights* effectively. |
| **Language** | **JavaScript/Shell (MongoDB)** | Used for writing and executing the aggregation *queries*. |

## 💾 Data Source and Scope

*   **Dataset:** Brazilian Federal Government Budget (Expenditure Data).
*   **Source:** Kaggle (publicly available).
*   **Period Analyzed:** 2014 (with scope for analysis across complete fiscal years).
*   **Volume:** Thousands of expenditure records.
*   **Scope:** Analysis of multiple federal ministries.

## ⚙️ Methodology and Data Engineering

The data preparation phase was crucial and involved the following steps, using the Aggregation Framework:

1.  **Type Conversion (`$toDouble`, `$convert`):** Monetary values were stored as *strings*. It was necessary to convert them to the `double` type to allow for precise mathematical calculations.
2.  **Cleaning and Filtering (`$match`):** Removal of incomplete, null, or empty records that could skew the results.
3.  **Exception Handling:** Implementation of logic to avoid "Division by Zero" errors in execution percentage calculations.

## ❓ Business Questions and Key Insights

Our project was structured to answer three strategic questions, each revealing an aspect of budget management:

### 1. What is the average budget execution rate for each ministry?

**Objective:** To understand which ministries are most efficient at spending what was planned.

**Main Query:** Grouping by ministry (`$group`) to sum authorized and executed values, followed by calculating the execution percentage and sorting (`$sort`).

**Key Insights:**

| Efficiency Group | Execution Percentage | Ministry Examples | Strategic Conclusion |
| :--- | :--- | :--- | :--- |
| **Efficiency Champions** | Above 90% | Defense, Foreign Affairs, Health, Finance | Demonstrate impeccable planning and organized resource management. |
| **On the Right Track** | Between 80% and 90% | Education, Infrastructure, Social Dev. | There is room for optimization and overcoming minor operational obstacles. |
| **Warning Sign** | Below 80% | Tourism (the lowest), Environment, Agriculture | Urgent need for auditing and review of planning and execution processes to avoid underutilization of funds. |

### 2. Which programs receive and spend the most resources each year?

**Objective:** To identify governmental priorities and the allocation of the largest volume of resources.

**Main Query:** Grouping by year and program, sorting by authorized value, and using `$slice` and `$unwind` to extract the Top 5 annual programs.

**Key Insights:**

*   **Constant Priorities:** Programs related to **Public Health (SUS)**, **Education**, and **Infrastructure** consistently appear at the top, reflecting essential areas for continuous investment.
*   **Flexibility:** The analysis allows for the identification of specific programs introduced in response to crises or emergency needs (e.g., pandemics, natural disasters).
*   **Impact:** The concentration of resources in these areas confirms that public investment is directed toward essential services that directly affect the population's lives.

### 3. Which ministries show the greatest percentage variation between authorized and executed budgets?

**Objective:** To identify ministries with the most difficulty aligning planning (authorized) with the reality of execution (spending).

**Main Query:** Calculation of the percentage variation by year and ministry, followed by the calculation of the average variation over time (`$avg`).

**Key Insights:**

*   **High Variation:** Ministries such as **Tourism**, **Environment**, and **Agriculture** lead the variation ranking.
*   **Potential Causes:** High variation may indicate budget overestimation, operational difficulties (bureaucracy, lack of personnel), or frequent unforeseen events.
*   **Recommendation:** The control agency should initiate dialogue with high-variation ministries to understand the causes and propose more realistic planning and more efficient execution strategies.

## 🚀 Conclusion

The project demonstrated the ability to transform a complex set of raw data into actionable **business intelligence**. The use of the **MongoDB Aggregation Framework** not only facilitated data manipulation and analysis but also enabled the creation of complex and robust analysis *pipelines*, essential for the oversight and improvement of public management.

**Data Analysis is not just about numbers; it's about telling a story that can change how public money is managed.**

---

**Developed by:** [Augusto Ogawa] and [Lucas Jose Pauk] (As per the report)
**Course:** Software Engineering
**Date:** October/2025 (As per the report)
