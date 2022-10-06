Lab Assignment 3 Instructions: 
 
Exercises 
 
We assume you have already installed MySQL server and Workbench, as well as the My Guitar Shop database with original data. In these exercises, you’ll use MySQL Workbench to work on the My Guitar Shop database and submit queries to this database. 
 
Code summary queries 
1.	Write a SELECT statement that returns these columns:   
The count of the number of orders in the Orders table   
The sum of the tax_amount columns in the Orders table   

![image](https://user-images.githubusercontent.com/99063625/194417047-3a176da3-fdb1-4592-9965-c59247c12a44.png)

2.	Write a SELECT statement that returns one row for each category that has products with these columns: 
The category_name column from the Categories table 
The count of the products in the Products table 
The list price of the most expensive product in the Products table Sort the result set so the category with the most products appears first. 
3.	Write a SELECT statement that returns one row for each customer that has orders with these columns: 
The email_address column from the Customers table 
The sum of the item price in the Order_Items table multiplied by the quantity in the Order_Items table 
The sum of the discount amount column in the Order_Items table multiplied by the quantity in the Order_Items table 
Sort the result set in descending sequence by the item price total for each customer. 
4.	Write a SELECT statement that returns one row for each customer that has orders with these columns: 
The email_address column from the Customers table 
A count of the number of orders 
The total amount for each order (Hint: First, subtract the discount amount from the price. Then, multiply by the quantity.) 
Return only those rows where the customer has more than 1 order. 
Sort the result set in descending sequence by the sum of the line item amounts. 
5.	Modify the solution to exercise 4 so it only counts and totals line items that have an item_price value that’s greater than 400. 
6.	Write a SELECT statement that answers this question: What is the total amount ordered for each product? Return these columns: 
The product_name column from the Products table 
The total amount for each product in the Order_Items table (Hint: You can calculate the total amount by subtracting the discount amount from the item price and then multiplying it by the quantity) 
Use the WITH ROLLUP operator to include a row that gives the grand total. 
Note: Once you add the WITH ROLLUP operator, you may need to use MySQL Workbench’s Execute SQL Script button instead of its Execute Current Statement button to execute this statement. 
7.	Write a SELECT statement that answers this question: Which customers have ordered more than one product? Return these columns: 
The email_address column from the Customers table 
The count of distinct products from the customer’s orders 
Sort the result set in ascending sequence by the email_address column. 
8.	Write a SELECT statement that answers this question: What is the total quantity purchased for each product within each category? Return these columns: 
The category_name column from the category table 
The product_name column from the products table 
The total quantity purchased for each product with orders in the Order_Items table 
Use the WITH ROLLUP operator to include rows that give a summary for each category name as well as a row that gives the grand total. 
Use the IF and GROUPING functions to replace null values in the category_name and product_name columns with literal values if they’re for summary rows.  
9.	Write a SELECT statement that uses an aggregate window function to get the total amount of each order. Return these columns: 
The order_id column from the Order_Items table 
The total amount for each order item in the Order_Items table (Hint: You can calculate the total amount by subtracting the discount amount from the item price and then multiplying it by the quantity) 
The total amount for each order 
Sort the result set in ascending sequence by the order_id column. 
10.	Modify the solution to exercise 9 so the column that contains the total amount for each order contains a cumulative total by item amount. 
Add another column to the SELECT statement that uses an aggregate window function to get the average item amount for each order. 
Modify the SELECT statement so it uses a named window for the two aggregate functions. 
 
Code subqueries 
11.	Write a SELECT statement that returns the same result set as this SELECT statement, but don’t use a join. Instead, use a subquery in a WHERE clause that uses the IN keyword. 
SELECT DISTINCT category_name 
FROM categories c JOIN products p 
  ON c.category_id = p.category_id 
ORDER BY category_name 
12.	Write a SELECT statement that answers this question: Which products have a list price that’s greater than the average list price for all products? 
Return the product_name and list_price columns for each product. 
Sort the result set by the list_price column in descending sequence. 
13.	Write a SELECT statement that returns the category_name column from the Categories table. 
Return one row for each category that has never been assigned to any product in the Products table. To do that, use a subquery introduced with the NOT EXISTS operator. 
14.	Write a SELECT statement that returns three columns: email_address, order_id, and the order total for each customer. To do this, you can group the result set by the email_address and order_id columns. In addition, you must calculate the order total from the columns in the Order_Items table. Write a second SELECT statement that uses the first SELECT statement in its FROM clause. The main query should return two columns: the customer’s email address and the largest order for that customer. To do this, you can group the result set by the email_address. Sort the result set by the largest order in descending sequence. 
15.	Write a SELECT statement that returns the name and discount percent of each product that has a unique discount percent. In other words, don’t include products that have the same discount percent as another product. 
Sort the result set by the product_name column. 
16.	Use a correlated subquery to return one row per customer, representing the customer’s oldest order (the one with the earliest date). Each row should include these three columns: email_address, order_id, and order_date. 
Sort the result set by the order_date and order_id columns. 
 
Process data types 
17.	Write a SELECT statement that returns these columns from the Products table: 
The list_price column 
A	column that uses the FORMAT function to return the list_price column with 1 digit to the right of the decimal point 
A column that uses the CONVERT function to return the list_price column as an integer 
A column that uses the CAST function to return the list_price column as an integer 
18.	Write a SELECT statement that returns these columns from the Products table: 
The date_added column 
A	column that uses the CAST function to return the date_added column with its date only (year, month, and day) 
A column that uses the CAST function to return the date_added column with just the year and the month 
A column that uses the CAST function to return the date_added column with its full time only (hour, minutes, and seconds). 
 
Use functions 
19.	Write a SELECT statement that returns these columns from the Products table: 
The list_price column 
The discount_percent column 
A	column named discount_amount that uses the previous two columns to calculate the discount amount and uses the ROUND function to round the result so it has 2 decimal digits 
20.	Write a SELECT statement that returns these columns from the Orders table: 
The order_date column 
A	column that uses the DATE_FORMAT function to return the four-digit year that’s stored in the order_date column 
A column that uses the DATE_FORMAT function to return the order_date column in this format: Mon-DD-YYYY. In other words, use abbreviated months and separate each date component with dashes. 
A column that uses the DATE_FORMAT function to return the order_date column with only the hours and minutes on a 12-hour clock with an am/pm indicator A column that uses the DATE_FORMAT function to return the order_date column in this format: MM/DD/YY HH:SS. In other words, use two-digit months, days, and years and separate them by slashes. Use 2-digit hours and minutes on a 24-hour clock. And use leading zeros for all date/time components. 
21.	Write a SELECT statement that returns these columns from the Orders table: 
The card_number column 
The length of the card_number column 
When you get that working right, add the columns that follow to the result set. This is more difficult because these columns require the use of functions within functions. 
The last four digits of the card_number column 
A	column that displays an X for each digit of the card_number column except for the last four digits. If the card number contains 16 digits, it should be displayed in this format: XXXX-XXXX-XXXX-1234, where 1234 are the actual last four digits of the number. If the card number contains 15 digits, it should be displayed in this format: 
XXXX-XXXXXX-X1234. (Hint: Use an IF function to determine which format to use.) 
22.	Write a SELECT statement that returns these columns from the Orders table: 
The order_id column 
The order_date column 
A	column named approx_ship_date that’s calculated by adding 2 days to the order_date column 
The ship_date column if it doesn’t contain a null value 
A column named days_to_ship that shows the number of days between the order date and the ship date 
When you have this working, add a WHERE clause that retrieves just the orders for March 2018. 
23.	Write a SELECT statement that uses regular expression functions to get the username and domain name parts of the email addresses in the Administrators table. Return these columns: 
The email_address column 
A	column named user_name that contains the username part of the email_address column (the part before the @ symbol) 
A column named domain_name that contains the domain name part of the email_address column (the part after the @ symbol) 
Note: The username part of the email addresses contains only letters, and the domain name part contains only letters and a period. 
24.	Write a SELECT statement that uses the ranking functions to rank products by the total quantity sold. 
Return these columns: 
The product_name column from the Products table 
A	column named total_quantity that shows the sum of the quantity for each product in the 
Order_Items table 
A column named rank that uses the RANK function to rank the total quantity in descending sequence  
A column named dense_rank that uses the DENSE_RANK function to rank the total quantity in descending sequence  
25.	Write a SELECT statement that uses the analytic functions to get the highest and lowest sales by product within each category. Return these columns: 
The category_name column from the Categories table 
The product_name column from the Products table 
A	column named total_sales that shows the sum of the sales for each product with sales in the Order_Items table 
A column named highest_sales that uses the FIRST_VALUE function to show the name of the product with the highest sales within each category  
A column named lowest_sales that uses the LAST_VALUE function to show the name of the product with the lowest sales within each category.  
 
Lab Report Deliverables 
 
In the lab report, you must include the following contents: 
•	Create one screen shot for each of the steps 1 – 25 (2 pts each). 
•	Your screen shots must include the complete SQL command syntax and the result grid (the results shown in the grid can be incomplete) 
 
Name the completed lab report as “LastNameFirstInitialLab3Report” (e.g., MaiBLab3Report.docx).  Submit the Lab report file (Word or PDF format) via the Canvas Lab 3 submission link before the due time. 
