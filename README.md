# financial-fraud-detection-sql
# Financial Fraud Detection — SQL Analysis

End-to-end fraud analysis project developed using **SQL Server**, focused on identifying
fraud patterns, risk exposure, and behavioral signals in transactional data.

This project simulates a real-world scenario where a financial institution aims to
better understand fraudulent behavior in order to support risk mitigation and
decision-making.

---

## 🏢 Business Context

Financial institutions process millions of transactions daily and must continuously
monitor fraud risk to minimize financial losses and protect customers.

In this simulated scenario, the company wants to answer key questions such as:
- How frequent is fraud within transactions?
- What behavioral patterns are associated with fraudulent activity?
- Does identity data availability reduce fraud risk?
- Are there time-based or device-related fraud patterns?

The analysis was designed as if requested by **risk and fraud stakeholders**.

---

## 📊 Dataset Overview

The project uses the **IEEE-CIS Fraud Detection dataset**, which contains:
- Transaction-level financial data
- Identity and device-related attributes
- Fraud labels (`isFraud`)

Main tables used:
- `train_transaction`
- `train_identity`

---

## 📂 Project Structure

