 📊 Power BI Sales Performance Dashboard

🧾 Project Overview  
This Power BI dashboard provides an interactive visual representation of a company's sales performance. It enables stakeholders to track key metrics such as total sales, profit, quantity sold, and discounts across various dimensions like product categories, regions, and customer behavior.

📁 Dataset Structure

| Column Name     | Description                                   |
|-----------------|-----------------------------------------------|
| OrderID         | Unique identifier for each order              |
| OrderDate       | Date of order placement                       |
| CustomerName    | Name of the customer                          |
| Product         | Product name                                  |
| Category        | Product category (e.g., Furniture, Technology)|
| Sales           | Revenue generated from the order              |
| Quantity        | Number of units sold                          |
| Discount        | Discount applied on the product               |
| Profit          | Profit gained from the sale                   |
| Region          | Geographical region of the sale               |

📌 Key Features
- Total Sales, Total Profit, Quantity, and Discount KPIs
- Monthly Sales Trend (line or column chart using DAX: DATESMTD)
- Top 6 Products by Sales (stacked column chart)
- Sales by Region (Map with Region as Location and Category as Legend)
- Sales Distribution by Category (Treemap)
- Interactive Filters:
  - Category slicer
  - Region slicer
  - Date range slicer

🧠 DAX Measures Used

Total Sales = SUM('SalesData'[Sales])

Total Profit = SUM('SalesData'[Profit])

Monthly Sales = 
CALCULATE(
    [Total Sales],
    DATESMTD('SalesData'[OrderDate])
)

Top 6 Products by Sales = 
TOPN(6, 
    SUMMARIZE('SalesData', 'SalesData'[Product], "SalesAmount", [Total Sales]),
    [SalesAmount], DESC
)

📌 Visuals Used

| Visual Type       | Purpose                                |
|-------------------|----------------------------------------|
| Card              | KPIs like Total Sales, Profit, etc.    |
| Stacked Column    | Product-wise or Monthly Sales          |
| Treemap           | Category-wise sales                    |
| Map               | Regional sales performance             |
| Slicer            | For filtering by Category, Region, etc.|

✅ How to Use
1. Open the .pbix file in Power BI Desktop.
2. Connect your dataset (if not already loaded).
3. Use slicers to filter and explore different views.
4. Hover over charts/maps for detailed tooltips.

📦 Future Enhancements
- Add Year-over-Year comparison
- Integrate customer demographics
- Predictive sales analytics using AI visual

