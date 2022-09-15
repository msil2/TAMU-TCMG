# Lab Assignment 2

## Exercises

We assume you have already installed MySQL server and Workbench, as well as the My Guitar Shop database. In these exercises, you’ll use MySQL Workbench to work on the My Guitar Shop database, to submit queries to this database, and to create EER models for databases.

### Retrieve data from a single table

1. Write a SELECT statement that returns four columns from the Products table: product_code, product_name, list_price, and discount_percent, and sorts the result set by list price in descending sequence. Then, run this statement to make sure it works correctly.

2. Write a SELECT statement that returns one column from the Customers table named full_name that joins the last_name and first_name columns. 

   Format this column with the last name, a comma, a space, and the first name like this: `Doe, John`
   
   Sort the result set by the last_name column in ascending sequence.
   
   Return only the customers whose last name begins with letters from M to Z. NOTE: When comparing strings of characters, ‘M’ comes before any string of characters that begins with ‘M’. For example, ‘M’ comes before ‘Murach'.
   
3. Write a SELECT statement that returns these columns from the Products table: product_name, list_price, date_added.
      
   Return only the rows with a list price that's greater than 500 and less than 2000.
   
   Sort the result set by the date_added column in descending sequence.
   
4. Write a SELECT statement that returns these column names and data from the Products table: product_name, list_price, discount_percent, discount_amount (calculated from the previous two columns), discount_price (calculated from the previous three columns).
   
   Round the discount_amount and discount_price columns to 2 decimal places.
   
   Sort the result set by the discount_price column in descending sequence.
   
   Use the LIMIT clause so the result set contains only the first 5 rows.
   
5. Write a SELECT statement that returns these column names and data from the Order_Items table: item_id, discount_amount, quantity, price_total (multiply item price by quantity), discount_total (multiply discount amount by quantity), item_total (subtract discount amount from item price, then multiply by quantity).
 
   Only return rows where the item_total is greater than 500.
   
   Sort the result set by the item_total column in descending sequence.
   
6. Write a SELECT statement that returns these columns from the Orders table: order_id, order_date, ship_date.

   Return only the rows where the ship_date column contains a null value.
   
7. Write a SELECT statement without a FROM clause that creates a row with these columns:
