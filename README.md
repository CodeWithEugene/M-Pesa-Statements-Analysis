# M-Pesa-Statements-Analysis

## Overview
M-Pesa, Kenya's leading mobile money service, powers everyday payments. 
I dug into my M-Pesa statements for the year 2024 to see where my money went — spoiler alert: a lot went to M-Shwari and mutura!😂
I cleaned the data, categorized my spending (Send Money, Pochi La Biashara, Till Numbers, Paybills), calculated the total amount I spent on transaction costs for the, created interactive visualizations with Plotly Express and so much more.
Click on M_Pesa_Statements_Analysis.ipynb to view the analysis.

## Dataset
The data comes from `2024_MPesa_Statements.csv`(which is basically my M-Pesa statement for the year 2024).
The data has the following with columns:
- `Receipt_No`: Transaction ID
- `Completion_Time`: Date and time of transaction
- `Details`: Transaction description
- `Transaction_Status`: Status of transaction
- `Received`: Money received (KES)
- `Withdrawn`: Money spent (KES)
- `Balance`: Account balance (KES)
Unfortunately I cannot include the dataset here for personal reasons. If you need data for such a project you can always request a yearly M-Pesa statement using MY Safaricom app.

## Objectives
To find:
- Total money received and spent.
- Spending breakdown by category (e.g., Send Money, Paybill).
- Monthly and daily spending patterns, including my highest spending day.
- Transaction costs and daily averages.
- Fun analysis: How much I spent on mutura!

## Methodology
### 1. Data Cleaning
- Dropped unnecessary `Unnamed` columns.
- Converted `Received`, `Withdrawn`, and `Balance` to floats, handling commas and negatives (used `.abs()` for withdrawals).
- Transformed `Completion_Time` into `Date` and `Time` columns using `pd.to_datetime`.

### 2. Analysis
- **Totals**: Summed `Received` and `Withdrawn` for net earnings (-KES 15,453).
- **Categories**: Grouped spending into Send Money, Pochi la Biashara, Till Numbers, Paybill Numbers, M-Shwari Deposits, and Airtime Purchases.
- **Monthly Spending**: Aggregated by month, sorted chronologically.
- **Daily Spending**: Identified highest spending day (9 Sept 2024, KES 23,099, excluding M-Shwari and Send Money).
- **Transaction Costs**: Calculated using M-Pesa tariffs, averaged 6.14 transactions and KES 8.32 daily.
- **Mutura Purchases**: Filtered for vendor "GIDRAPH GACIBU"(my mutura plug), counted 62 transactions.

### 3. Visualization
Interactive Plotly charts:
- Bar chart: Spending by category.
- Bar chart: Monthly spending.
- Line chart: Daily spending.
- Bar chart: Monthly transaction costs.
- Grouped bar chart: Mutura purchases by month.

## Key Findings
| Metric                          | Value                   |
|---------------------------------|-------------------------|
| Total Received                  | KES 965,967.00          |
| Total Spent                     | KES 981,420.00          |
| Net Earnings                    | KES -15,453.00          |
| Top Category                    | M-Shwari Deposits (KES 405,296) |
| Highest Spending Day            | 9 Sept 2024 (KES 23,099) |
| Transaction Costs               | KES 2,836.00            |
| Avg. Daily Transactions         | 6.14                    |
| Avg. Daily Transaction Cost     | KES 8.32                |
| Mutura Spending                 | KES 3,370 (62 times)    |

- **Highest Spending Day**: Paid school fees on 9 Sept 2024 (KES 23,099).
- **Most Spent On**: School fees via Paybill (KES 48,900).
- **Peak Month**: December (KES 216,869—Christmas vibes! 😎).

## How to Run
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/CodeWithEugene/M-Pesa-Analysis-2024.git
   cd M-Pesa-Analysis-2024