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
   
7. Write a SELECT statement without a FROM clause that creates a row with these columns: price, (100 dollars) tax_rate (.07), tax_amount (price multiplied by tax), total (price plus tax).

   To calculate the fourth column, add the expressions you used for the first and third columns.
   
### Retrieve data from multiple tables

8. Write a SELECT statement that joins the Customers table to the Addresses table and returns these columns: first_name, last_name, line1, city, state, zip_code.

   Return one row for each address for the customer with an email address of allan.sherwood@yahoo.com.
   
9. Write a SELECT statement that joins the Customers table to the Addresses table and returns these columns: first_name, last_name, line1, city, state, zip_code.

   Return one row for each customer, but only return addresses that are the shipping address for a customer.
   
10. Write a SELECT statement that joins the Customers, Orders, Order_Items, and Products tables. This statement should return these columns: last_name, first_name, order_date, product_name, item_price, discount_amount, and quantity. 

    Use aliases for the tables. 
   
    Sort the final result set by the last_name, order_date, and product_name columns.
   
11. Write a SELECT statement that returns the product_name and list_price columns from the Products table.

    Return one row for each product that has the same list price as another product. Hint: Use a self-join to check that the product_id columns aren’t equal but the list_price columns are equal.
   
   
    Sort the result set by the product_name column
   
12. Write an INSERT statement that adds this row to the Categories table: category_name: Brass 

    Code the INSERT statement so MySQL automatically generates the category_id column.
    
14. Write an UPDATE statement that modifies the row you just added to the Categories table. This statement should change the product_name column to “Woodwinds”, and it should use the category_id column to identify the row.

15. Write a DELETE statement that deletes the row you added to the Categories table in exercise 1. This statement should use the category_id column to identify the row.

16. Write an INSERT statement that adds this row to the Products table: product_id (The next automatically generated ID), category_id (4), product_code (dgx_640), product_name (Yamaha DGX 640 88-Key Digital Piano), description (Long description to come), list_price (799.99), discount_percent (0), date_added (Today’s date/time).

    Use a column list for this statement.
    
17. Write an UPDATE statement that modifies the product you added in step 16. This statement should change the discount_percent column from 0% to 35%.

18. Write a DELETE statement that deletes the Keyboards category. When you execute this statement, it will produce an error since the category has related rows in the Products table. To fix that, precede the DELETE statement with another DELETE statement that deletes all products in this category. (Remember that to code two or more statements in a script, you must end each statement with a semicolon.

19. Write an INSERT statement that adds this row to the Customers table: email_address (rick@raven.com), password (empty string), first_name (Rick), last_name (Raven).

    Use a column list for this statement.
    
20. Write an UPDATE statement that modifies the Customers table. Change the password column to “secret” for the customer with an email address of rick@raven.com

21. Open the script named create_my_guitar_shop.sql that’s in the mgs_ex_starts directory. Then, run this script. That should restore the data that’s in the database.

### Design a database

22. Use MySQL Workbench to create an EER model from the script file named create_my_guitar_shop.sql that’s in the mgs_ex_starts folder. 

    From the model, create an EER diagram that shows the relationships between the seven tables in the database. (The administrators table is not related to the other six tables.)
    
23. Use MySQL Workbench to create an EER model for a database that stores information about the downloads that users make. (When you create the EER model, it will be given a default name of mydb. For this exercise, it’s not necessary to change this name.) Define the tables that are necessary to implement this data structure:

    Each user must have an email address, first name, and last name.

    Each user can have one or more downloads.

    Each download must have a filename and download date/time.

    Each product can be related to one or more downloads.

    Each product must have a name.

    When you’re done defining the tables, create a diagram for the database. Then, use the diagram to define the required relationships. When you do that, be sure to use the relationship button that uses existing columns.

24. Use MySQL Workbench to open the EER model that you created in step 23. Then, export a script that creates the database. Use all the default options, and save the script in a file named Lab2.sql.
