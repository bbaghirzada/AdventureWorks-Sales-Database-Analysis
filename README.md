# AdventureWorks Sales Dashboard and Revenue Trends Analysis

## Overview
This project showcases the creation of a **Sales Dashboard** and a **PowerPoint Presentation** for AdventureWorks, a fictional company. The dashboard and presentation provide actionable insights into revenue trends, customer segments, and sales performance. The data was extracted and analyzed using **SQL queries** from the AdventureWorks database.

The project demonstrates my ability to:
- Extract and analyze data using SQL.
- Visualize data using Tableau.
- Present insights in a clear and professional manner with PowerPoint.

---

## Project Components

### 1. AdventureWorks Sales Dashboard
A dynamic and interactive dashboard created using Tableau. The dashboard visualizes key sales metrics, including:
- **Revenue Growth Trends**: Historical and current revenue performance.
- **Customer Segments**: Analysis of revenue by customer type (individual vs. wholesale).
- **Regional Performance**: Sales performance across different regions(Europe, USA and Australia).
- **Sales Channel Distribution**: Effectiveness of online vs. offline sales channels.

### 2. Revenue Trends and Online Sales PowerPoint Presentation
A comprehensive presentation summarizing the analysis and insights derived from the sales data. Key sections include:
- **Revenue Growth Patterns**: Analysis of revenue trends and digital market expansion.
- **Customer Behavior**: Insights into customer preferences and purchasing patterns.
- **Regional Sales Performance**: Variations in sales performance across regions.
- **SWOT Analysis**: Strengths, weaknesses, opportunities, and threats for the business.

### 3. SQL Queries
Custom SQL queries were used to extract and analyze data from the AdventureWorks database. These queries formed the foundation for the dashboard and presentation.

---

## Key Insights

### Revenue Trends and Customer Segments
- **Consistent Revenue Growth**: The company has shown steady revenue growth, driven by successful digital market expansion since 2003.
- **Customer Preferences**: Individual customers tend to make online purchases, while partners prefer wholesale contracts and offline sales.

### Sales Channel Distribution and Regional Performance
- **Effective Sales Channels**: Online sales channels have proven highly effective, contributing significantly to revenue growth.
- **Regional Variations**: Sales performance varies across regions, highlighting the need for region-specific strategies.

### Customer Segments and Product Category Sales
- **Segmented Sales Analysis**: Understanding sales performance by customer segment enables targeted marketing and product development.
- **Regional Demand**: Regional analysis reveals variations in consumer preferences and demand for specific product categories.

### SWOT Analysis
- **Strengths**: Strong revenue growth and successful digital market expansion.
- **Weaknesses**: Limited performance in certain regions and gaps in customer segment targeting.
- **Opportunities**: Leveraging regional insights and focusing on high-value customer segments and online sales due to the big price difference.
- **Threats**: Market saturation and evolving consumer preferences.

---

## Tools and Technologies Used
- **Data Extraction and Analysis**: SQL for querying the AdventureWorks database.
- **Data Visualization**: Tableau for creating the sales dashboard.
- **Presentation**: Microsoft PowerPoint for summarizing insights.
- **Data Source**: AdventureWorks database (fictional dataset).

---

## SQL Queries Used
Below are the SQL queries used to extract and analyze data for this project:

### Query 1: Customer and Address Details
```sql
SELECT 
    c.customerID AS customerID,
    c.customerType,
    c.addressID,
    ca.addressTypeID,
    atp.name AS addressTypeName
FROM 
    tc-da-1.adwentureworks_db.customer c
LEFT JOIN 
    tc-da-1.adwentureworks_db.customeraddress ca
    ON c.customerID = ca.customerID
LEFT JOIN 
    tc-da-1.adwentureworks_db.addresstype atp
    ON atp.addresstypeID = ca.addresstypeID
ORDER BY 
    c.customerID;
```

### Query 2: Purchase Order Details
```sql
SELECT 
    poh.purchaseorderID AS porderid,
    poh.shipmethodid,
    poh.vendorid,
    pod.productid,
    pod.unitprice,
    pod.linetotal,
    pod.receivedqty,
    pod.rejectedqty,
    pod.stockedqty
FROM 
    tc-da-1.adwentureworks_db.purchaseorderheader poh
LEFT JOIN 
    tc-da-1.adwentureworks_db.purchaseorderdetail pod
    ON poh.purchaseorderid = pod.purchaseorderid;
```

### Query 3: Vendor and Product Information
```sql
SELECT 
    v.vendorid,
    v.name AS vendorName,
    v.creditrating,
    v.activeflag,
    vc.contactid,
    vc.contacttypeid,
    pv.productid
FROM 
    tc-da-1.adwentureworks_db.vendor v
LEFT JOIN 
    tc-da-1.adwentureworks_db.vendorcontact vc
    ON v.vendorid = vc.vendorid
LEFT JOIN 
    tc-da-1.adwentureworks_db.productvendor pv
    ON v.vendorid = pv.vendorid;
```
