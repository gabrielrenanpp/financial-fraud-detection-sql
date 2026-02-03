<p align="center">
  <img src="assets/Fraud%20detection.png" alt="Financial Fraud Detection" width="700">
</p>


# Financial Fraud Detection — SQL Analysis

This project is framed around a simulated financial institution that processes a high volume of online transactions and must continuously manage fraud risk to protect both revenue and customers. Using the IEEE-CIS Fraud Detection dataset as a proxy for real-world transactional and identity data, the analysis applies SQL Server to investigate fraud prevalence, financial exposure, and behavioral patterns across transactions. By combining transaction-level information with identity and device signals, the project mirrors how fraud and risk teams explore data to support monitoring strategies, risk mitigation, and informed business decision-making.

---

## 🏢 Business Context

Financial institutions process millions of transactions daily and must continuously
monitor fraud risk to minimize financial losses and protect customers.


This simulated scenario aims to answer key questions such as:

• How frequent is fraud within transactions?

• What transaction-level behavioral patterns are associated with fraudulent activity?

• Does identity data availability reduce fraud risk?

• Are there device-related fraud patterns across transactions?

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

This query creates a consolidated analytical dataset by combining transaction-level information with identity and device attributes. Establishing a unified base ensures that all subsequent analyses are consistent, enriched with contextual signals, and aligned with how fraud is evaluated in real-world scenarios.

### Comparison of Transaction Amounts: Fraud vs. Legitimate

<p align="left">
  <img src="https://github.com/gabrielrenanpp/Image/blob/main/fourth%20image.png?raw=true" width="600">
</p>

This analysis compares transaction value patterns between fraudulent and legitimate activity using average and median metrics, highlighting structural differences while reducing the influence of outliers.

---

### Fraud Distribution by Transaction Amount Ranges

<p align="left">
  <img src="https://github.com/gabrielrenanpp/Image/blob/main/fifth%20image.png?raw=true" width="600">
</p>

This analysis evaluates how fraud frequency varies across transaction value ranges, highlighting whether certain transaction sizes are more vulnerable to fraudulent activity.

---
### Fraud Rate by Identity Data Presence

<p align="left">
  <img src="https://github.com/gabrielrenanpp/Image/blob/main/sixth%20image.png?raw=true" width="600">
</p>

This query assesses whether the availability of identity data is associated with differences in fraud risk, providing insight into the value of identity enrichment in fraud prevention.

---
### Fraud Rate by Device Type

<p align="left">
  <img src="https://github.com/gabrielrenanpp/Image/blob/main/seventh%20image.png?raw=true" width="600">
</p>

---
### Identity-Based Risk Signal (id_03)

<p align="left">
  <img src="https://github.com/gabrielrenanpp/Image/blob/main/eighth%20image.png?raw=true" width="600">
</p>
This query examines an identity-related attribute as a potential fraud risk indicator, supporting segmentation and feature selection for downstream fraud models.

---

## Conclusion
This analysis shows that fraud, while representing a smaller share of total transactions, accounts for a disproportionate amount of financial exposure, reinforcing the need to evaluate risk beyond simple transaction counts. Fraudulent activity exhibits distinct transaction value patterns, with differences in average, median, and value-range distributions when compared to legitimate behavior. The presence of identity data is strongly associated with higher fraud detection, highlighting its importance in improving fraud visibility rather than increasing fraud occurrence. Additionally, fraud incidence varies across device types and identity segments, indicating that contextual and identity-related attributes are meaningful risk signals. Overall, the results demonstrate that effective fraud detection relies on combining transaction behavior with identity and device context to support data-driven risk mitigation and decision-making.
