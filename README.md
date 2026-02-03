<p align="center">
  <img src="assets/Fraud%20detection.png" alt="Financial Fraud Detection" width="700">
</p>


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

The project uses the **[IEEE-CIS Fraud Detection dataset](https://www.kaggle.com/c/ieee-fraud-detection)**, a large-scale, real-world dataset originally released for a Kaggle competition focused on identifying fraudulent online transactions.

This dataset contains:

- Transaction-level financial data
- Identity and device-related attributes
- Fraud labels (`isFraud`)

Main tables used in this analysis:

- `train_transaction`
- `train_identity`


---

## 📂 Project Structure

---
### Base Analytical CTE

<p align="left">
  <img src="https://github.com/gabrielrenanpp/Image/blob/main/first%20image.png?raw=true" width="600">
</p>

<p align="left">
  <img src="https://github.com/gabrielrenanpp/Image/blob/main/Second%20Image.png?raw=true" width="600">
</p>

This query creates the analytical base used throughout the project.
It standardizes the core transaction fields and ensures consistent data types for analysis.

The column TransactionID uniquely identifies each transaction in the dataset.
TransactionAmt represents the monetary value of the transaction and is cast to a numeric format suitable for aggregation.
isFraud is the fraud label, where 1 indicates a fraudulent transaction and 0 indicates a legitimate one.
TransactionDT represents the number of seconds elapsed since the first transaction in the dataset and is used for time-based analysis.
DeviceType indicates the type of device used to perform the transaction.

This base ensures that all subsequent queries operate on a clean and reliable structure.
---
 ### Overall Fraud Rate and Financial Exposure

<p align="left">
  <img src="https://github.com/gabrielrenanpp/Image/blob/main/Third%20Image.png?raw=true" width="600">
</p>

This query provides a high-level view of fraud exposure in the business.

It shows how many transactions were processed, how many were fraudulent, and the percentage of fraud within total activity. In addition, it quantifies the total financial volume at risk by comparing fraudulent transaction value against overall transaction value.

Together, these metrics allow stakeholders to quickly assess how frequent fraud is and how much money is exposed, supporting risk prioritization and strategic decision-making.

