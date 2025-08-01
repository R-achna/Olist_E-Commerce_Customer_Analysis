# Olist E-commerce Customer Lifetime Value (CLTV) & Retention Strategy

### 1. Overview

This project focuses on analyzing customer behavior for the Olist E-commerce platform to understand customer value and retention. By segmenting customers, predicting their lifetime value, and analyzing retention patterns, the goal is to provide data-driven strategies to optimize marketing efforts, improve customer retention, and maximize profitability.

**Goal:**

- To segment Olist's customer base into distinct groups based on their purchasing behavior.
- To calculate and analyze Customer Lifetime Value (CLTV).
- To understand customer retention patterns over time.
- To propose actionable, data-driven strategies to enhance customer value and loyalty.

![Olist_CLTV_Strategy_Report_page-0001](https://github.com/user-attachments/assets/f8573618-3767-4fc4-9bf7-24b10e03add6)

### 2. Data Source

The dataset used in this project is the "Brazilian E-commerce Public Dataset by Olist" available on Kaggle. It provides real-world transactional data from Olist stores, covering orders, products, customers, sellers, payments, and reviews.

- **Source:** [Kaggle: Olist Brazilian E-commerce Public Dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)
- **Time Period:** October 2016 to August 2018

### 3. Methodology & Project Structure

The project follows a structured approach:

- `00_data_ingestion.ipynb`: Initial loading of raw CSV files.
- `01_data_cleaning_and_preparation.ipynb`: Extensive data cleaning, handling missing values, standardizing formats, and merging relevant tables into a master dataset.
- `02_eda_and_data_profiling.ipynb`: Exploratory Data Analysis to understand data distributions, identify outliers, and gain initial insights.
- `03_rfm_cltv_calculation.ipynb`:
    - **RFM Analysis:** Calculating Recency, Frequency, and Monetary values for each unique customer.
    - **Customer Segmentation:** Applying quintile-based or custom rules to segment customers into groups like 'Champions', 'Loyal', 'At Risk', 'New Customers', etc.
    - **Historical CLTV Calculation:** Summing up the total revenue generated by each customer.
    - **Cohort Analysis:** Grouping customers by acquisition month and tracking their retention rate over subsequent months.
    
    ```python
    olist-ecommerce-cltv-strategy/
    ├── data/
    ├       └── notebooks/               # Jupyter Notebooks for EDA, Cleaning, RFM/CLTV calculations
    │   ├── 01_data_loading_eda.ipynb
    │   ├── 02_data_cleaning_translation.ipynb
    │   ├── 03_rfm_cltv_calculation.ipynb
    │   └── processed/            # Cleaned, translated, and possibly joined CSVs/Parquet files
    │       ├── olist_master_data_cleaned.csv
    |       ├── olist_customer_rfm_cltv.csv
    │       └── olist_cohort_retention_pivot.csv 
    ├── dashboards/               # Power BI files
    │   └── Olist_CLTV_Strategy_Dashboard.pbix
    │   └── Olist_CLTV_Strategy_Report.pdf
    └── [README.md](http://readme.md/)                 # Your project's summary and impact statement
    ```
    

### 4. Key Findings & Insights

- **Customer Segmentation:**
    - The largest customer segments are 'Others/Lost' (24%)  and 'At Risk' (23.8%), highlighting a significant one-time buyer base and potential churn issues."
    - The 'Champions' segment, despite being only 1.05 % of the customer base, contributes disproportionately to total historical revenue, confirming their high value."
- **Retention Analysis:**
    - Olist experiences a steep drop-off in customer retention after the first month, indicating a need for stronger post-purchase engagement."
    - Older cohorts (e.g., 2017 cohorts) show slightly better long-term retention compared to newer ones, suggesting potential shifts in customer behavior or acquisition strategies."
- **Deeper Segment Insights (Based on Product/Review/Payment Analysis):**
    - Champions frequently purchase products in the 'health_beauty' and 'telephony' categories, suggesting opportunities for targeted cross-selling."
    - Customers in 'At Risk' and 'Hibernating' segments exhibit lower average review scores (e.g., 3.5 vs. 4.5 for Champions), indicating that negative experiences might be a key driver of churn.
    - Credit card is the predominant payment method across all segments, but specific segments might show slight variations.
      
  Report: https://drive.google.com/file/d/1tHi5r64Jr1mvVqqA2ZCM085RTY_dxelt/view?usp=drive_link

### 5. Strategic Recommendations

- **Enhance New Customer Onboarding & Early Retention:**
    - Implement a multi-channel onboarding campaign (email, push notifications) for 'New Customers' focused on post-purchase support and encouraging a second purchase within 30 days, to improve Month 1 retention.
- **Cultivate High-Value Customers ('Champions' & 'Loyal Customers'):**
    - Develop a loyalty program for 'Champions' offering exclusive discounts, early access to new products, or personalized recommendations to maximize their CLTV and reduce churn.
- **Re-engage 'At Risk' & 'Hibernating' Customers:**
    - Launch targeted win-back campaigns for 'At Risk' and 'Hibernating' segments with personalized offers based on their last purchase or category preferences. Consider addressing common pain points identified (e.g., if low review scores are a factor, offer specific service recovery).
- **Improve Product/Service Quality:**
    - Investigate the root causes of lower review scores among 'At Risk' segments, potentially focusing on specific product categories or logistical issues that lead to dissatisfaction.
## 6. Tools & Technologies Used
- **Python**: Pandas, NumPy, Matplotlib, Seaborn
- **Power BI**: Interactive dashboard design
- **Jupyter Notebooks**: Data analysis pipeline
- **Excel**: Intermediate verification
