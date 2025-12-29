# Sales and Customer Behavior Insights

## Project Overview

This project analyzes retail sales data to uncover actionable insights about customer purchasing behavior, product performance, and operational efficiency. The analysis covers end-to-end data processing from raw data cleaning to business intelligence visualization.

## Business Objectives

- Identify revenue drivers across regions and product categories
- Analyze customer behavior patterns by loyalty tier
- Evaluate delivery performance and operational bottlenecks
- Flag underperforming products for strategic review

## Dataset

The analysis utilizes three interconnected datasets:

| Dataset | Records | Description |
|---------|---------|-------------|
| Sales Data | 3,000 | Transaction records with order details |
| Product Info | 30 | Product catalog with categories and pricing |
| Customer Info | 500 | Customer demographics and loyalty information |

### Key Variables

- **Sales**: order_id, customer_id, product_id, quantity, unit_price, order_date, delivery_status, payment_method, region, discount_applied
- **Product**: product_id, product_name, category, launch_date, base_price, supplier_code
- **Customer**: customer_id, email, signup_date, gender, region, loyalty_tier

## Methodology

### 1. Data Cleaning and Preprocessing

- Standardized text fields (Title Case normalization)
- Converted date columns to datetime format
- Handled missing values with appropriate imputation strategies
- Corrected data entry errors and typos
- Validated numeric constraints (quantity >= 0, discount between 0-1)

### 2. Data Integration

- Merged three datasets using LEFT JOIN on product_id and customer_id
- Final integrated dataset: 2,989 records with 20 features

### 3. Feature Engineering

| Feature | Description | Calculation |
|---------|-------------|-------------|
| revenue | Net sales amount | quantity × unit_price × (1 - discount) |
| order_week | Week number of order | Extracted from order_date |
| price_band | Price tier classification | Low (<15), Medium (15-30), High (>30) |
| days_to_order | Product adoption speed | order_date - launch_date |
| is_late | Delivery delay indicator | delivery_status == 'Delayed' |

### 4. Exploratory Data Analysis

- Regional revenue distribution analysis
- Category-wise performance comparison
- Customer segmentation by loyalty tier
- Payment method preferences across segments
- Delivery performance metrics by region and price band

## Key Findings

### Revenue Performance

| Region | Total Revenue |
|--------|---------------|
| South | $49,732 |
| East | $48,013 |
| West | $47,730 |
| Central | $47,575 |
| North | $46,778 |

### Category Analysis

| Category | Revenue | Quantity | Avg Discount |
|----------|---------|----------|--------------|
| Cleaning | $93,772 | 3,589 | 8.6% |
| Storage | $47,169 | 1,736 | 8.1% |
| Outdoors | $40,062 | 1,519 | 8.2% |
| Kitchen | $33,934 | 1,226 | 7.6% |
| Personal Care | $24,892 | 900 | 8.7% |

### Operational Insights

- Overall delivery delay rate: approximately 39%
- Credit Card is the preferred payment method across all loyalty tiers (45-67%)
- Gold tier customers account for the highest order volume

### Underperforming Products

Identified 4 products with low sales volume, high discount dependency, and elevated delay rates requiring strategic review.

## Visualizations

The analysis includes the following visualizations:

1. Weekly Revenue Trends by Region (Bar Chart)
2. Top Categories by Revenue (Bar Chart)
3. Revenue by Category and Region (Grouped Bar Chart)
4. Quantity Distribution by Category and Discount (Box Plot)
5. Correlation Matrix: Revenue, Discount, Quantity (Heatmap)
6. Orders by Loyalty Tier and Region (Count Plot)
7. Delivery Status by Price Band (Stacked Bar Chart)
8. Delivery Delay Rate by Region (Bar Chart)

## Technical Stack

| Technology | Purpose |
|------------|---------|
| Python 3.11 | Programming language |
| Pandas | Data manipulation and analysis |
| NumPy | Numerical computing |
| Matplotlib | Base visualization library |
| Seaborn | Statistical data visualization |
| Scikit-learn | Data preprocessing (MinMaxScaler) |

## Project Structure

```
sales-customer-behaviour-insights/
├── data/
│   ├── sales_data.csv
│   ├── product_info.csv
│   └── customer_info.csv
├── src/
│   └── sales-customer-behaviour-insights.ipynb
└── README.md
```

## Business Recommendations

1. **Logistics Optimization**: Address the 39% delivery delay rate, particularly in East and North regions
2. **Category Strategy**: Leverage Cleaning category success; investigate Personal Care underperformance
3. **Customer Retention**: Develop targeted programs for Gold tier customers who drive majority of orders
4. **Product Portfolio**: Review flagged underperforming products for discontinuation or repositioning

## How to Run

1. Clone the repository
2. Install required packages: `pip install pandas numpy matplotlib seaborn scikit-learn`
3. Open the Jupyter notebook in `src/` directory
4. Run all cells sequentially

## Author

Jiyoon Moon
