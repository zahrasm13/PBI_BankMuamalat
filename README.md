# PBI_BankMuamalat
 Sales Report for 2020 and 2021 PT Sejahtera Bersama

## Challenge
One of the main projects as a Business Intelligence Intern at Bank Muamalat is to create sales report for 2020 and 2021. Here are the steps of the project:

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

### 3.  Create Dashboard Performance Analytics Kimia Farma Business Year 2020-2023
https://github.com/zahrasm13/PBI_BankMuamalat/blob/main/PBI_Bank%20Muamalat.pdf 

