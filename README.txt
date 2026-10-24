# ☕ Coffee Shop Business Analytics

An end-to-end data analytics project focused on cleaning coffee shop business data, analyzing sales performance, understanding customer purchasing behavior, and monitoring inventory using Python, Pandas, Jupyter Notebook, and Microsoft Power BI.

## 📌 Project Overview

This project transforms raw coffee shop data into structured datasets and business insights. It demonstrates a practical data analytics workflow, from identifying data quality issues to preparing cleaned datasets, calculating key performance indicators (KPIs), and building an interactive Power BI dashboard.

The project focuses on helping business owners understand sales trends, product performance, customer behavior, payment preferences, store performance, and inventory conditions.

## 🎯 Objectives

- Clean and validate raw sales, customer, and inventory datasets.
- Identify duplicate records, missing values, and invalid data.
- Analyze revenue, orders, and quantities sold.
- Compare sales performance across product categories and store locations.
- Explore customer purchasing behavior.
- Analyze payment methods and inventory status.
- Build an interactive Power BI dashboard for business monitoring.
- Present the results in a reproducible and organized project structure.

## 🛠️ Tools and Technologies

| Tool | Purpose |
|---|---|
| Python | Data processing and analysis |
| Pandas | Data cleaning and manipulation |
| Jupyter Notebook | Exploratory analysis and documentation |
| Microsoft Power BI | Interactive dashboard and visual reporting |
| DAX | KPI calculations in Power BI |
| Power Query | Data transformation and date preparation |
| CSV | Data storage and exchange |
| Git and GitHub | Version control and project sharing |

## 📂 Project Structure

```text
coffee_shop_capstone/
│
├── sales_raw.csv
├── customers_raw.csv
├── inventory_raw.csv
│
├── sales_clean.csv
├── customers_clean.csv
├── inventory_clean.csv
│
├── coffee_shop_analysis.ipynb
├── coffee_shop_kpi_summary.csv
├── data_cleaning_log.csv
├── inventory_analysis.csv
├── inventory_summary.csv
│
├── csba.pbix
└── README.md
```

### File Descriptions

- **Raw CSV files:** Original sales, customer, and inventory datasets.
- **Cleaned CSV files:** Processed datasets prepared for analysis.
- **`coffee_shop_analysis.ipynb`:** Python notebook containing the analysis workflow.
- **`coffee_shop_kpi_summary.csv`:** Summary of key performance indicators.
- **`data_cleaning_log.csv`:** Record of data quality checks and cleaning actions.
- **`inventory_analysis.csv`:** Detailed inventory analysis output.
- **`inventory_summary.csv`:** Summary of inventory metrics.
- **`csba.pbix`:** Power BI dashboard file.
- **`README.md`:** Project documentation.

## 📊 Dataset Description

The project uses three related datasets.

### 1. Sales Dataset

Contains transaction-level sales information, including:

- Order ID and order date/time
- Customer ID and product ID
- Product name and category
- Quantity and unit price
- Discount percentage
- Line revenue
- Payment method
- Store location

### 2. Customer Dataset

Contains customer information used to explore customer profiles and purchasing behavior, including customer identifiers and available profile attributes.

### 3. Inventory Dataset

Contains product inventory information used to examine stock levels and inventory management, including available opening stock, received stock, sold units, waste, closing stock, reorder levels, and unit costs.

## 🧹 Data Cleaning and Preparation

Data quality checks were performed before analysis.

Key tasks included:

- Identifying and removing duplicate records.
- Checking missing customer IDs, unit prices, and payment methods.
- Identifying invalid quantities and prices.
- Standardizing missing customer profile values.
- Checking inventory records for duplicates and invalid values.
- Preserving unknown inventory values rather than automatically treating them as zero.
- Exporting cleaned datasets for further analysis.

### Sales Data Quality Summary

The initial sales dataset contained 20,229 rows.

| Data quality check | Records identified |
|---|---:|
| Exact duplicate rows | 81 |
| Missing customer IDs | 120 |
| Missing unit prices | 61 |
| Missing payment methods | 80 |
| Zero or negative quantities | 6 |
| Negative unit prices | 6 |

After cleaning, the final sales dataset contained **20,136 rows**. These checks and cleaning actions are documented in the project outputs.

## 🔍 Analysis Performed

### Sales Performance
- Total revenue
- Total orders
- Units sold
- Average order value
- Monthly revenue trends

### Product and Category Analysis
- Revenue by product category
- Comparison of category performance
- Identification of products contributing to sales

### Store Performance
- Revenue comparison across store locations
- Analysis of differences in store-level performance

### Customer Insights
- Identified customer counts
- Customer-level revenue analysis
- Top customers by revenue
- Exploration of purchasing patterns

### Payment Analysis
- Comparison of payment methods, including cash, card, wallet, and UPI
- Examination of payment preferences

### Inventory Analysis
- Opening, received, sold, and closing stock analysis
- Reorder-level monitoring
- Inventory value analysis where the required data is available
- Review of stock discrepancies and waste

## 📈 Power BI Dashboard

The project includes an interactive dashboard saved as `csba.pbix`.

The dashboard incorporates the following KPI measures:

```dax
Total Revenue =
SUM(sales_clean[line_revenue])
```

```dax
Total Orders =
DISTINCTCOUNT(sales_clean[order_id])
```

```dax
Units Sold =
SUM(sales_clean[quantity])
```

```dax
Average Order Value =
DIVIDE([Total Revenue], [Total Orders], 0)
```

The dashboard work includes:

- KPI cards
- Monthly revenue trend
- Revenue by product category
- Store performance comparison
- Date-based filtering
- Payment-method analysis
- Customer revenue insights

The Power BI file can be downloaded from the repository and opened in Microsoft Power BI Desktop.

## 🚀 How to Run the Project

### Prerequisites

Install Python and the required analysis libraries. Jupyter Notebook or Visual Studio Code can be used to run the notebook.

### Step 1: Clone the Repository

Replace `YOUR_USERNAME` with your GitHub username and use the actual repository name.

```bash
git clone https://github.com/YOUR_USERNAME/coffee_shop_capstone.git
```

### Step 2: Open the Project

```bash
cd coffee_shop_capstone
```

### Step 3: Create a Virtual Environment (Optional)

```bash
python -m venv .venv
```

Activate it on Windows:

```powershell
.venv\Scripts\activate
```

### Step 4: Install Dependencies

```bash
python -m pip install pandas numpy matplotlib seaborn jupyter
```

Install any additional libraries required by the notebook if necessary.

### Step 5: Run the Notebook

```bash
jupyter notebook coffee_shop_analysis.ipynb
```

Alternatively, open `coffee_shop_analysis.ipynb` directly in Visual Studio Code and select an appropriate Python kernel.

### Step 6: Open the Dashboard

Open `csba.pbix` in Microsoft Power BI Desktop to explore the dashboard.

**Note:** The CSV files are included in the repository, so check that the notebook and Power BI file use the correct local file paths when opening the project on another computer.

## 💡 Business Value

This project demonstrates how data analytics can support coffee shop operations by helping decision-makers:

- Monitor revenue and order performance.
- Compare store and product category results.
- Understand customer purchasing behavior.
- Review payment-method usage.
- Identify potential inventory and stock-management issues.
- Make more informed, data-driven business decisions.

The dashboard and analysis provide a foundation for further work, such as demand forecasting, customer segmentation, product profitability analysis, and inventory optimization.

## ⚠️ Limitations

- Findings depend on the quality and coverage of the available datasets.
- Missing or unknown values may limit some analyses.
- Inventory discrepancies require further operational validation.
- Revenue analysis is based on the recorded `line_revenue` field.
- Any gross profit estimate based on inventory unit costs should be treated cautiously because the available inventory snapshot may not align exactly with the sales period and does not account for all operating expenses.

## 🔮 Future Improvements

- Add sales forecasting using machine learning.
- Perform customer segmentation using clustering.
- Analyze peak sales hours and days.
- Build product-level profitability analysis.
- Improve inventory demand forecasting and reorder recommendations.
- Automate data refresh and dashboard updates.

## 👨‍💻 Author

**Your Name**

MCA Student | Aspiring Data Analyst

GitHub: [Your GitHub Profile](https://github.com/YOUR_USERNAME)

## 📄 License

This project is intended for educational and portfolio purposes. Add an appropriate open-source license if you want others to reuse, modify, or distribute the project.

