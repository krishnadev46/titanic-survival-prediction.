# Customer Behavior Analysis

An end-to-end data analytics project that explores customer purchasing behavior using **Python, SQL (PostgreSQL), and Power BI**, with findings summarized in a report and a presentation.

---

## Overview

This project analyzes customer transaction data to understand who the customers are, what they buy, and how much they spend. The goal is to turn raw data into clear business insights about revenue, sales, subscriptions, and customer segments.

**Key questions answered:**
- Which product categories generate the most revenue and sales?
- Which age groups contribute the most to revenue?
- How many customers have an active subscription?
- What is the average review rating and purchase amount?

---

## Dataset

- **Source:** [Add dataset name / link, e.g. Kaggle]
- **Size:** ~3.9K customer records
- **Key columns:**

| Column | Description |
|---|---|
| Customer ID | Unique customer identifier |
| Age / Age Group | Customer age and segment (Young Adult, Adult, Middle-aged, Senior) |
| Gender | Male / Female |
| Category | Accessories, Clothing, Footwear, Outerwear |
| Purchase Amount (USD) | Amount spent per purchase |
| Review Rating | Customer rating of the purchase |
| Subscription Status | Yes / No |
| Shipping Type | 2-Day, Express, Free Shipping, Next Day Air, Standard, Store Pickup |

---

## Tools Used

| Tool | Purpose |
|---|---|
| **Python** (Pandas, NumPy) | Data loading, EDA, and cleaning |
| **PostgreSQL** | Storing data and running analytical SQL queries |
| **Power BI** | Interactive dashboard |
| **Gamma** | Presentation (PPT) |
| **GitHub** | Version control and portfolio hosting |

---

## Steps

1. **Load the data** into Python using Pandas.
2. **Exploratory Data Analysis (EDA):** inspect structure, summary statistics, and distributions.
3. **Data cleaning:** handle missing values (e.g. review ratings), fix column names, and create age groups.
4. **Load into PostgreSQL** and run SQL queries for revenue, sales, and customer segments.
5. **Build the Power BI dashboard** connected to the database.
6. **Create the report and presentation** summarizing insights and recommendations.

---

## Dashboard

The Power BI dashboard includes:

- **KPIs:** Number of customers (3.9K), Average review rating (3.75), Average purchase amount ($59.76)
- **Visuals:** % of customers by subscription status, Revenue by category, Sales by category, Revenue by age group, Sales by age group
- **Slicers:** Subscription status, Gender, Category, Shipping type

![Dashboard](images/dashboard.png)

---

## Results

- **Clothing** is the top category for both revenue and sales, followed by Accessories, Footwear, and Outerwear.
- About **73%** of customers are not subscribed, while **27%** are, which shows room to grow subscriptions.
- **Young adults and middle-aged customers** contribute the most revenue.
- The average customer spends about **$59.76** per purchase and rates products around **3.75 / 5**.

**Recommendations:**
- Promote subscriptions to the large non-subscribed base.
- Focus marketing on Clothing and top-performing age groups.
- Look for ways to lift the lower-performing Outerwear category.

---

## How to Run

1. **Clone the repository**
   ```bash
   git clone https://github.com/krishnadev46/customer-trends-data-analysis.git
   cd customer-trends-data-analysis
   ```
2. **Install Python dependencies**
   ```bash
   pip install pandas numpy matplotlib seaborn jupyter
   ```
3. **Run the notebook** for EDA and cleaning
   ```bash
   jupyter notebook
   ```
4. **Set up the database:** create a PostgreSQL database, import the cleaned dataset, and run the queries in the `sql/` folder.
5. **Open the dashboard:** open `customer_behavior.pbix` in Power BI Desktop and update the data source connection if needed.

---

## Project Structure

```
├── data/                    # Raw and cleaned datasets
├── notebooks/               # Python EDA and cleaning
├── sql/                     # SQL queries
├── dashboard/               # Power BI file (.pbix)
├── images/                  # Dashboard screenshots
├── report/                  # Project report
├── presentation/            # PPT made with Gamma
└── README.md
```

---

## Author

**[Your Name]**
[LinkedIn](https://linkedin.com/in/your-profile) | [GitHub](https://github.com/krishnadev46)
