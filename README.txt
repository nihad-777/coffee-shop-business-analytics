# Coffee Shop Business Analytics Capstone — Simulated Dataset

All records are synthetic and created for learning. They do not describe a real business or real people.

## Files
- `sales_raw.csv`: transaction line items across calendar year 2025. One order can have multiple rows because an order may contain multiple products.
- `customers_raw.csv`: customer profile and signup data.
- `inventory_raw.csv`: stock snapshot with units sold, closing stock, reorder level, supplier, and waste.

## Intentional data-quality issues
The files deliberately include a small number of duplicate rows, missing values, inconsistent capitalization/whitespace, mixed date formats, zero quantities, negative unit prices, and an invalid negative waste value. Identify and document each issue before deciding how to handle it.

## Important definitions
- `line_revenue` is the recorded revenue for a sales line after discount.
- `unit_price` is the listed price per unit before discount.
- `unit_cost` is product cost per unit in the inventory file. For an approximate line-level gross profit, join sales to inventory on `product_id`, then calculate `line_revenue - quantity * unit_cost`. This is an educational estimate, not audited accounting profit.
- Inventory is a simplified snapshot. `units_sold` is calculated from the clean generated sales records, while stock and waste are simulated.
- Customer retention/churn is inferred from the latest purchase date in the sales data; it is not a confirmed cancellation or customer statement.

## Suggested first steps
1. Load all three files in pandas.
2. Inspect `.shape`, `.head()`, `.info()`, `.isna().sum()`, and duplicate counts.
3. Create a cleaning log before making changes.
4. Save cleaned outputs separately; never overwrite the raw files.
