Sales & Customer Behaviour Insights — Green Cart Ltd.
Project Overview
This project analyses sales transactions, product information, and customer information for Green Cart Ltd., a UK-based e-commerce business specialising in eco-friendly household products. The work was completed as a Week 2 Data Analytics Project in June 2026.

The aim is to clean and combine the available datasets, engineer useful analytical features, and identify insights that can support sales growth, customer retention, marketing decisions, and delivery operations.
Business Questions
The analysis explores:
1. Which product categories generate the most revenue, and which regions perform best?
2. Do discounts relate to the number of items customers purchase?
3. Which loyalty tier generates the most revenue?
4. Which regions experience the highest delivery-delay rates?
5. Do customer signup cohorts show differences in purchasing activity?
Datasets
The notebook uses three CSV files:
- sales_data.csv — order and transaction records.
- product_info.csv — product details, categories, launch dates, and supplier information.
- customer_info.csv — customer details, signup dates, loyalty tiers, and related attributes.
Place these files in a data/ directory in the project folder, or update the notebook's file paths to match your local setup. Do not upload private or sensitive customer information to a public repository.
Tools and Libraries
- Python
- pandas
- NumPy
- Matplotlib
- Seaborn
- scikit-learn (MinMaxScaler for revenue normalisation)
- Jupyter Notebook
Install the main dependencies with:
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
Project Workflow
1. Data inspection and cleaning
The analysis inspects dataset structure, missing values, duplicates, and descriptive statistics. Cleaning steps include:
- Standardising delivery-status, payment-method, product-category, loyalty-tier, and gender values.
- Converting order, product-launch, and customer-signup dates to datetime format.
- Filling missing discount values with 0 where appropriate.
- Handling missing categorical values using Unknown where appropriate.
- Checking transaction quantities, unit prices, discounts, and product/customer records.
2. Data integration
The sales records are left-joined with product information using product_id, then with customer information using customer_id. Left joins are used to preserve sales transactions while adding available product and customer attributes.
3. Feature engineering
The notebook creates analytical features including:
Feature	Description
revenue	Quantity × unit price × (1 − discount applied)
order_week	ISO week extracted from the order date
price_band	Low (under £15), Medium (£15–£30), or High (over £30)
days_to_order	Days between product launch and order date
email_domain	Domain extracted from the customer email address
is_late	Indicates whether the delivery status is delayed
signup_month	Month in which the customer signed up
revenue_scaled	Revenue normalised with MinMaxScaler


4. Exploratory analysis
The project examines revenue by product category, region, and loyalty tier; discount and quantity patterns; delivery delays; signup cohorts; and products that may be underperforming.
Key Findings
The following figures are reported in the accompanying project report and should be interpreted in the context of the supplied datasets.
- Cleaning was the highest-revenue category, generating £93,825.89.
- Gold loyalty members generated the most revenue, at £137,092.17, compared with £52,367.01 for Silver and £49,086.04 for Bronze.
- The East region had the highest reported delivery-delay rate, at 41.7%.
- The reported correlation between discount and quantity sold was approximately −0.008, indicating virtually no linear relationship in this dataset.
- The strongest signup-month revenue cohorts reported were August 2024 (£24,008.72), February 2025 (£23,829.38), October 2024 (£22,479.31), and November 2024 (£22,427.76).
Recommendations
Based on the analysis:
1. Prioritise cleaning products in relevant merchandising and marketing plans, while monitoring performance by region.
2. Strengthen loyalty engagement and test targeted incentives that may encourage Bronze and Silver members to increase their engagement.
3. Investigate delivery operations in the East region, including fulfilment processes and logistics performance.
4. Evaluate promotions with controlled comparisons rather than assuming discounts increase purchase quantity.
5. Improve data quality at source through consistent category values, date formats, validation rules, and automated data-quality checks.
How to Run
1. Clone or download this repository.
2. Install the dependencies listed above.
3. Place the three input CSV files in the expected location.
4. Open the notebook in Jupyter:
   jupyter notebook
5. Open the project notebook and run the cells in order.
Path note: The original notebook may contain local Windows file paths. Update the pd.read_csv(...) statements for your machine, or use relative paths such as data/sales_data.csv, data/product_info.csv, and data/customer_info.csv.
Limitations
- Findings depend on the completeness and quality of the supplied data.
- The discount–quantity correlation describes association, not causation.
- Signup-cohort revenue differences do not by themselves prove that signup timing caused higher spending.
- The reported regional delay rates should be reviewed alongside order counts and operational context.
- The project is an exploratory analysis, not a live production reporting system.
Repository Contents
Suggested repository structure:
sales-customer-behaviour-insights/
├── README.md
├── customer-behaviour-2(3).ipynb
└── data/
    ├── sales_data.csv
    ├── product_info.csv
    └── customer_info.csv
Author
Paul Anyira
Data Analytics Project — Week 2
June 2026
