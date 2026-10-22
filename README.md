# Credit Card Customer & Transaction Analysis (EDA)

Exploratory data analysis of a credit card dataset covering **1,000 customers** and **500,000 transactions**, with a focus on data cleaning, outlier handling, and customer/spending behavior insights.

## Datasets
| File | Description |
|------|-------------|
| `customers.csv` | Demographics: age, gender, location, occupation, income, marital status |
| `credit_profiles.csv` | Credit score, utilisation, outstanding debt, inquiries, credit limit |
| `transactions.csv` | Date, amount, platform, product category, payment type |

Customer data was loaded from a **MySQL** database; the rest from CSV.

## Tech Stack
Python · Pandas · NumPy · Matplotlib · Seaborn · MySQL (`mysql.connector`) · Jupyter

## Data Cleaning Highlights
- **Annual income:** filled 50 missing values with the occupation-wise median; replaced unrealistic values (< 100) the same way
- **Age:** replaced impossible ages (< 15 or > 80) with occupation-wise median; created age groups (18-25, 26-48, 49-65)
- **Credit profiles:** removed duplicate customer records; imputed missing credit limits using the mode per credit-score range
- **Outstanding debt:** capped values exceeding credit limit
- **Transactions:** filled missing platforms with the mode; replaced zero-amount transactions with a group median; capped amounts above the customer's credit limit

## Analysis & Visualizations
- Income distribution and average income by gender, location, marital status, and occupation
- Customer distribution by age group, location, and gender
- Credit score vs. credit limit relationship and correlation heatmap
- Product category by platform
- Payment type, product category, and platform preferences by age group

## Key Takeaways
- Credit limit is strongly correlated with credit score (~0.85) and outstanding debt (~0.81)
- Occupation is the main driver of income differences (Business Owners and Data Scientists lead)
- Most customers are male, city-based, and aged 26-48

## How to Run
1. Clone the repo and place CSVs in a `dataset/` folder
2. Update the MySQL connection details (or load customers from CSV)
3. Run `credit_card-analysis.ipynb`

## Next Steps
Customer segmentation, credit risk modeling, and an interactive dashboard.
