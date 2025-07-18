Product Sales Insights 📊

A SQL-based data analytics project to generate product-level sales insights across cities and dates using simulated e-commerce data.

🔍 Project Overview

This project focuses on building a comprehensive data pipeline using SQL to extract, clean, and transform product-level sales data. The objective is to derive actionable insights such as inventory movement, store coverage, on-shelf availability, discount trends, and estimated revenue. The insights are useful for business intelligence teams, supply chain optimization, and pricing strategy.


---

📁 Dataset Overview

The project uses three base tables and creates one derived insights table:

1. productsalesraw

Raw sales and inventory data for each store, product, and date.

transactiondate: Date of transaction.

productid: Unique product identifier.

productname: Name of the product.

storecode: Store identifier.

saleprice: Selling price of the product.

mrp: Maximum Retail Price.

productquantity: Inventory available.

brandcode: Brand identifier.

brandname: Name of the brand.

unit: Packaging unit (e.g., kg, ml).

productimageurl: Link to product image.

maincategoryid: ID of the main product category.

subcategoryid: ID of the subcategory.


2. productcategories

Maps each product to its main and subcategories.

maincategoryid: Main category ID.

maincategory: Main category .

subcategoryid: Subcategory ID.

subcategory: Subcategory .


3. storelocationmapping

Maps each store to a city.

storecode: Store identifier.

cityname: Name of the city.


4. productsalesinsights (Derived Table)

Final output table containing analytical insights at city-date-product level.

transactiondate: Date of transaction.

productid: Unique product identifier.

cityname: City in which product was sold.

brandcode: Brand identifier.

brandname: Brand name.

productimageurl: Product image URL.

productname: Name of the product.

maincategoryid: Main category ID.

maincategory: Main category .

subcategoryid: Subcategory ID.

subcategory: Subcategory .

qtysold: Estimated quantity sold (using inventory LAG).

salessp: Estimated revenue from selling price.

salesmrp: Estimated revenue from MRP.

storelisted: Count of stores that listed the product.

storetotal: Total store count on that date.

osatotal: OSA = % of total stores with the product in stock.

osalisted: OSA = % of listed stores with the product in stock.

mrp: Minimum MRP for that product/date/city.

sp: Minimum selling price.

discount: Percentage discount from MRP.



---

⚙️ Core SQL Tasks

1. Data Cleaning & Importing

Converted date formats.

Handled store entries without city mappings.



2. Data Enrichment

Joined product, category, and location data.

Created a derived table at city × SKU × date level.



3. KPI Calculations

Estimated quantity sold using inventory LAG.

Calculated OSA (on-shelf availability) metrics.

Computed store counts and SKU listing counts.

Derived discount %, estimated revenue from MRP and SP.



4. Final Export

Cleaned nulls, filtered out irrelevant rows.

Exported to CSV using batch logic (50k–100k row chunks).





---

🛠️ Tools & Skills Used

SQL (MySQL 8.0)

Excel for data preview

Visual Studio Code / Notepad++ for reviewing exported files

Data Cleaning, ETL, Window Functions, Joins, Aggregation, Subqueries



---

📌 Use Cases

✅ Inventory Optimization
✅ Pricing & Promotion Effectiveness
✅ City-wise Demand Analysis
✅ product Listing & Stock Tracking


---

📂 Files in this Repository

File Name	Description

productsalesinsights_queries.txt	All SQL queries used to build the project
productsalesinsights_output.csv	Final result
README.md	Project documentation



---

💡 Future Improvements

Visualize insights using Power BI

Automate the pipeline using Python + MySQL

Apply clustering for customer or product segmentation



---

🙋‍♀️ About Me

Megha Soni
Aspiring Business/Data Analyst with hands-on experience in real-world data projects.
📫 meghasoni.me@gmail.com

