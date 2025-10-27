# Chargeback Monitoring & Risk Analysis

This project uses synthetic credit card transaction data to identify trends in fraudulent or high-risk transactions that may contribute to chargebacks.  
The goal is to monitor chargeback rates, detect emerging patterns, and ultimately **keep dispute ratios low to meet Visa and Mastercard compliance thresholds**.

By analyzing transaction data in Google BigQuery, this project simulates a typical workflow used in a Risk or Chargeback Operations team.

---

## 🗂 Project Structure



chargeback_data/
├─ queries/       # SQL queries used for analysis
├─ charts/        # Generated charts from analysis
└─ README.md      # Project overview and documentation



---

## 📊 Data

- **Source:** Synthetic dataset of 200–500 transactions  
- **Purpose:** Simulated credit card transaction data to explore chargeback and fraud correlations  
- **Columns:**  
  - `Time` – Transaction timestamp  
  - `V1` – Randomized feature (acts as a proxy for risk-related signal)  
  - `Amount` – Transaction amount in dollars  
  - `Class` – Chargeback indicator (`0 = non-chargeback`, `1 = chargeback/fraud`)  

---

## 🧠 Analysis Overview

Each query in the `queries/` folder supports part of the chargeback monitoring process:

1. **Transaction Summary** – Basic metrics including min/max/avg amounts and chargeback counts (`query_summary.sql`)  
2. **Chargeback Distribution** – Breakdown of total chargebacks vs non-chargebacks (`query_class_distribution.sql`)  
3. **Transaction Amount Stats** – Summary statistics across all transactions (`query_amount_stats.sql`)  
4. **Class-Based Statistics** – Compare chargeback vs non-chargeback transactions by amount (`query_class_amount_stats.sql`)  
5. **Amount Buckets** – Segment transactions into amount ranges to identify chargeback patterns (`query_amount_buckets.sql`)  
6. **Chargeback Rate by Amount Range** – Calculate and visualize the percentage of chargebacks within each amount bucket (`query_fraud_rate.sql`)  

---

## 📈 Charts

- `chart_bucket_class.png` – Transaction count per amount bucket, split by chargeback status  
- `graph_fraudrate_amount.png` – Chargeback rate (%) per transaction amount bucket  

These visualizations help identify which transaction ranges contribute disproportionately to chargebacks — a key insight for maintaining acceptable chargeback ratios under Visa/Mastercard rules.

---

## ⚙️ How to Run

1. Open your **Google BigQuery** project.  
2. Create a dataset and upload the synthetic `Transactions` table.  
3. Run the SQL queries from the `/queries` folder in order.  
4. Visualize the results in BigQuery or export them to charts.  

---

## ✅ Outcome

This project demonstrates a simplified version of how risk teams monitor transaction trends and chargeback ratios.  
The insights can guide **preventive strategies** (e.g., adjusting fraud filters, refund policies, or merchant onboarding criteria) to **reduce chargebacks and ensure compliance** with card network thresholds.

