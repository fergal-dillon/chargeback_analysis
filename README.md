# Chargeback Analysis

This project analyzes synthetic credit card transaction data to explore trends in fraudulent activity. The goal is to understand the distribution of transaction amounts and the occurrence of fraud.  

## Project Structure

chargeback_data/
├─ queries/       # SQL queries used for analysis
├─ charts/        # Generated charts from analysis
└─ README.md      # Project overview and documentation


## Data

- **Source:** Synthetic dataset of 200–500 transactions
- **Columns used:**  
  - `Time` – Timestamp of the transaction  
  - `V1` – Random feature for analysis  
  - `Amount` – Transaction amount  
  - `Class` – Fraud label (0 = non-fraud, 1 = fraud)

## Queries

The SQL queries in the `queries/` folder perform the following analyses:

1. **Transaction summary** – Minimum, maximum, average, total transactions, fraud vs non-fraud counts (`query_summary.sql`)  
2. **Class distribution** – Count and percentage of fraud vs non-fraud transactions (`query_class_distribution.sql`)  
3. **Amount statistics** – Minimum, maximum, average, median transaction amounts (`query_amount_stats.sql`)  
4. **Class-wise amount statistics** – Same stats split by Class (`query_class_amount_stats.sql`)  
5. **Amount buckets** – Transactions grouped into amount ranges with fraud counts (`query_amount_buckets.sql`)  
6. **Fraud rate by amount bucket** – Percentage of fraud within each amount bucket (`query_fraud_rate.sql`)  

## Charts

- `chart_bucket_class.png` – Count of transactions per amount bucket, split by Class  
- `graph_fraudrate_amount.png` – Fraud rate by transaction amount bucket  

## How to Run

1. Open your BigQuery project.  
2. Create the `Transactions` table and upload the dataset.  
3. Run the SQL queries in order for analysis.  
4. Generate charts based on query results.  
