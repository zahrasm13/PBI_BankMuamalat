# PBI_BankMuamalat
 Sales Report for 2020 and 2021 PT Sejahtera Bersama

## Company Background 
PT Sejahtera Bersama is a company focusing on developing innovative products; the company has launched several solutions that cover a wide range of categories, including blueprints, drone kits, drones, ebooks, robot kits, robots, and training videos. These products aim not only to meet the needs of the rapidly growing technology market but also to support education and technical skill development worldwide.

## Project Objective
The objective of this project is to provide an in-depth understanding of the sales performance of each product of PT Sejahtera Bersama during 2020 and 2021. Through sales data analysis, the company can identify new opportunities in the market.

## Challenge
One of the main projects as a Business Intelligence Intern at Bank Muamalat is to create sales report for 2020 and 2021. Here are the steps of the project:

### A. Determine the Primary Key (PK) of each dataset and create an Entity Relationship Diagram (ERD)
![Screenshot (374)](https://github.com/zahrasm13/PBI_BankMuamalat/assets/165493458/bfa36667-2be3-4417-a9f6-76e0908c1e58)
- Primary key Customer tabel : CustomerID
- Primary key Products tabel : ProdNumber
- Primary key Orders tabel : OrderID
- Primary key ProductCategory tabel : CategoryID

### B. Create a master table containing sales information and create a sales report dashboard

### 1. Importing Dataset to PostgreSQL
**Dataset** <br>
The provided dataset consists of the following tables:
- Products
- ProductCategory
- Orders
- Customers
  
### 2. Make Master Table
Here are the columns contained in the table:
● transaction_id : kode id transaksi, 
● category_name: kategori produk,
● product_name : nama produk, 
● product_price : harga produk, 
● order_date : tanggal transaksi dilakukan, 
● order_qty : kuantitas penjualan,
● total_sales : total penjualan, 
● cust_email : email pelanggan, 
● cust_city : kota pelanggan.


<details>
  <summary> Click to View Query </summary>
    <br>
    
```sql
SELECT
    o."Date" AS order_date,
    pc."CategoryName" AS category_name,
    p."ProdName" AS product_name,
    p."Price" AS product_price,
    o."Quantity" AS order_qty,
    p."Price" * o."Quantity" AS total_sales,
    c."CustomerEmail" AS cust_email,
    c."CustomerCity" AS cust_city
FROM public."Orders" AS o
JOIN public."Customers" AS c 
    ON c."CustomerID" = o."CustomerID"
JOIN public."Products" AS p 
    ON p."ProdNumber" = o."ProdNumber"
JOIN public."ProductCategory" AS pc 
    ON pc."CategoryID" = p."Category";
	
```
<br>
</details>
<br>

### 3.  Create Sales Report Dashboard
![Screenshot (375)](https://github.com/zahrasm13/PBI_BankMuamalat/assets/165493458/1e5a2341-dd7a-4a75-8a72-d189c9018bbd)

## C. Business Insight
- Sales Decline: 
There was a 7.7% decrease in sales from 2020 to 2021. This calls for an in-depth evaluation of the sales and marketing strategies carried out over the period.
- Monthly Sales Trend Analysis: 
The sales graph shows significant monthly fluctuations in product sales in 2020 and 2021. This indicates specific seasonal patterns or trends that need to be further understood.
- Top Product Categories: 
While the Robots product category has the highest sales revenue, the ebooks product category has the highest unit sales. This shows that while sales revenue can indicate success, sales volume must also be considered.
- City with the Highest Sales: 
Washington is the city with the highest total sales and total orders. This indicates significant market potential in the city.

## D. Business Recommendation
- Optimize Marketing Strategy: 
Need to conduct an in-depth evaluation of the marketing strategies that have been carried out to understand what is effective and what is not. 
- Bundle Package Sales:
Offer attractive bundle packages that include several products often purchased together or have complementary uses. 
- Promotions and Discounts: 
Use promotions and discounts to encourage impulse purchases and attract new customers.
- Expand Sales Channels: 
In addition to increasing marketing efforts, expanding sales channels can also be an effective strategy.
- Regional Expansion: 
Given the sales success in Washington, companies may consider regional expansion to other regions with the same or similar market potential. 

