# pizza-sales-sql-analysis


## 📊 Project Overview
This project provides a comprehensive end-to-end data analysis of a pizza restaurant's sales performance. Using **MySQL**, I transformed raw CSV datasets into a relational database to extract actionable business insights. The analysis progresses from foundational metrics (KPIs) to advanced trend analysis and complex ranking using Window Functions and CTEs.

## 🎯 Business Objectives
The goal of this analysis was to answer key business questions, such as:
- What is the total revenue and order volume?
- Which pizza sizes and categories drive the most sales?
- What are the peak hours for restaurant operations?
- How does revenue grow cumulatively over time?
- Which specific pizzas are the top performers within each category?

## 📂 Repository Structure
- `data/`: Contains the 4 raw CSV files used for the analysis.
- `sql_scripts/`: 
    - `01_schema_setup.sql`: Database and table creation scripts.
    - `02_basic_analysis.sql`: Foundation KPIs and metrics.
    - `03_intermediate_analysis.sql`: Trend analysis and groupings.
    - `04_advanced_analysis.sql`: Complex analytics using Window Functions.
- `README.md`: Project documentation.

## 🛠️ Tech Stack
- **Database:** MySQL
- **Tool:** MySQL Workbench
- **Language:** SQL (Structured Query Language)

## 🗄️ Database Schema & Data Dictionary
The project utilizes a relational schema consisting of four tables:



| Table Name | Description | Key Columns |
| :--- | :--- | :--- |
| **`orders`** | Daily record of all orders placed. | `order_id`, `date`, `time` |
| **`order_details`** | Granular details of pizzas within each order. | `order_id`, `pizza_id`, `quantity` |
| **`pizzas`** | Pricing and size variations for each pizza. | `pizza_id`, `pizza_type_id`, `size`, `price` |
| **`pizza_types`** | Descriptive data for pizza flavors and ingredients. | `pizza_type_id`, `name`, `category` |

## 🚀 Analysis Workflow

### 1. Foundational KPIs (Basic)
- Total order volume and gross revenue calculation.
- Identification of the highest-priced pizza and the most popular pizza size.
- Ranking the top 5 most ordered pizza flavors.

### 2. Operational Trends (Intermediate)
- Sales distribution by pizza category.
- **Hourly Traffic Analysis:** Identifying peak operational hours (found to be between 12:00 PM – 1:00 PM and evening blocks).
- Calculation of average pizzas ordered per day.

### 3. Strategic Insights (Advanced)
- **Revenue Contribution:** Percentage analysis of revenue by pizza category.
- **Growth Tracking:** Using `SUM() OVER()` to calculate cumulative revenue over time.
- **Segmented Ranking:** Identifying the top 3 revenue-generating pizzas within *each* category using `PARTITION BY`.

## 💡 Key Findings
- **High-Value Items:** The "Thai Chicken Pizza" is a major revenue driver, particularly in the Chicken category.
- **Popular Sizes:** "Large" pizzas account for the highest volume of orders compared to other sizes.
- **Peak Performance:** The restaurant experiences significant surges during the lunch hour (12-1 PM), suggesting a need for optimized staffing during this window.

---
