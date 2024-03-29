# Lab Assignment 5
 
## Exercises 
 
We assume you have already installed MySQL server and Workbench, as well as the My Guitar Shop database with original data. In these exercises, you’ll use MySQL Workbench to create stored objects.  

### Writing stored programs  

1. Write a script that creates and calls a stored procedure named test. This stored procedure should declare a variable and set it to the count of all products in the Products table. If the count is greater than or equal to 7, the stored procedure should display a message that says, “The number of products is greater than or equal to 7”. Otherwise, it should say, “The number of products is less than 7”.  

<p align="center">
  <img src="https://user-images.githubusercontent.com/99063625/202255493-ffe0e0b2-01f7-47db-af63-b4f274832191.png">
</p>

2. Write a script that creates and calls a stored procedure named test. This stored procedure should use two variables to store (1) the count of all of the products in the Products table and (2) the average list price for those products. If the product count is greater than or equal to 7, the stored procedure should display a result set that displays the values of both variables. Otherwise, the procedure should display a result set that displays a message that says, “The number of products is less than 7”.  

<p align="center">
  <img src="https://user-images.githubusercontent.com/99063625/202257274-85ebb781-e13c-4030-a80b-f41867917e7b.png">
</p>

3. Write a script that creates and calls a stored procedure named test. This procedure should calculate the common factors of the numbers 10 and 20. To find a common factor, you can use the modulo operator (%) to check whether a number that’s less than 10 can be evenly divided into both numbers. Then, this procedure should display a string that includes the common factors like this: 
   
   `Common factors of 10 and 20: 1 2 5` 
   
<p align="center">
  <img src="https://user-images.githubusercontent.com/99063625/202258180-9d517546-c13b-45f9-84c6-06df6897970c.png">
</p>
   
4. Write a script that creates and calls a stored procedure named test. This stored procedure should create a cursor for a result set that consists of the product_name and list_price columns for each product with a list price that’s greater than $700. The rows in this result set should be sorted in descending sequence by list price. Then, the procedure should display a string variable that includes the product_name and list price for each product so it looks something like this: 

   `"Gibson SG","2517.00"|"Gibson Les Paul","1199.00"|` 

   Here, each value is enclosed in double quotes ("), each column is separated by a comma (,) and each row is separated by a pipe character (|). 

<p align="center">
  <img src="https://user-images.githubusercontent.com/99063625/202260410-5c417407-7ba7-4820-8947-331d418052df.png">
</p>

5.  Write a script that creates and calls a stored procedure named test. This procedure should attempt to insert a new category named “Guitars” into the Categories table. If the insert is successful, the procedure should display this message: 
    
    `1 row was inserted.`
    
    If the update is unsuccessful, the procedure should display this message: 
    
    `Row was not inserted - duplicate entry.` 
 
<p align="center">
  <img src="https://user-images.githubusercontent.com/99063625/202261289-2bcbe05e-a04e-45d1-966e-fd1768801ae8.png">
</p> 
 
### Use transactions and locking 

6. Write a script that creates and calls a stored procedure named test. This procedure should include two SQL statements coded as a transaction to delete the row with a customer ID of 8 from the Customers table. To do this, you must first delete all addresses for that customer from the Addresses table. If these statements execute successfully, commit the changes, and display a message of 'The transaction was committed'. Otherwise, roll back the changes, and display a message of 'The transaction was rolled back'.  

<p align="center">
  <img src="https://user-images.githubusercontent.com/99063625/202263923-db508235-7644-435e-8a00-62e29aba9ead.png">
</p>

7. Write a script that creates and calls a stored procedure named test. This procedure should include these statements coded as a transaction: 
  
   ```
   INSERT INTO orders VALUES  
   (DEFAULT, 3, NOW(), '10.00', '0.00', NULL, 4,  
   'American Express', '378282246310005', '04/2016', 4);

   SELECT LAST_INSERT_ID()  
   INTO order_id; 
  
   INSERT INTO order_items VALUES  
   (DEFAULT, order_id, 6, '415.00', '161.85', 1);  
   
   INSERT INTO order_items VALUES  
   (DEFAULT, order_id, 1, '699.00', '209.70', 1); 
   ```
   
   Here, the LAST_INSERT_ID function is used to get the order ID value that’s automatically generated when the first INSERT statement inserts an order. 

   If these statements execute successfully, commit the changes, and display a message of 'The transaction was committed'. Otherwise, roll back the changes, and display a message of 'The transaction was rolled back'. 

<p align="center">
  <img src="https://user-images.githubusercontent.com/99063625/202282704-35642857-75d3-458c-b635-2982decb042b.png">
</p>

8. Write a script that creates and calls a stored procedure named test. This procedure should use a transaction that includes the statements necessary to combine two customers. These statements should do the following:  

   Select a row from the Customers table for the customer with a customer_id value of 6.  This statement should lock the row so other transactions can’t read or modify it until the transaction commits, and it should fail immediately if the row is locked from another session.  
   
   Update the Orders table so any orders for the selected customer are assigned to the customer with a customer_id value of 3.  
   
   Update the Addresses table so any addresses for the selected customer are assigned to the customer with a customer_id value of 3.  
   
   Delete the selected customer from the Customers table.  
   
   If these statements execute successfully, commit the changes, and display a message of 'The transaction was committed'. Otherwise, roll back the changes, and display a message of 'The transaction was rolled back'. 
 
 ![image](https://user-images.githubusercontent.com/99063625/202315174-edb99504-e93b-4f1c-bc79-130721ee69f9.png)

 
### Create stored procedures and functions 

9. Write a script that creates and calls a stored procedure named insert_category. First, code a statement that creates a procedure that adds a new row to the Categories table. To do that, this procedure should have one parameter for the category name.  
   
   Code at least two CALL statements that test this procedure. (Note that this table doesn’t allow duplicate category names). 
   
<p align="center">
  <img src="https://user-images.githubusercontent.com/99063625/202326783-980538ce-372b-4dc3-aca4-91dfc7f2746d.png">
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/99063625/202327695-d63663fa-ed18-4897-b3df-0734948aa8ec.png">
</p>

10.  Write a script that creates and calls a stored function named discount_price that calculates the discount price of an item in the Order_Items table (discount amount subtracted from item price). To do that, this function should accept one parameter for the item ID, and it should return the value of the discount price for that item. 

<p align="center">
  <img src="https://user-images.githubusercontent.com/99063625/202348402-a1e76706-0366-440e-8c02-4a0adc04bb25.png">
</p>

11.  Write a script that creates and calls a stored function named item_total that calculates the total amount of an item in the Order_Items table (discount price multiplied by quantity). To do that, this function should accept one parameter for the item ID, it should use the discount_price function that you created in exercise 2, and it should return the value of the total for that item. 

<p align="center">
  <img src="https://user-images.githubusercontent.com/99063625/202349183-f4fc15b1-e99b-479e-a001-e4ef600621e9.png">
</p>

12.  Write a script that creates and calls a stored procedure named insert_product that inserts a row into the Products table. This stored procedure should accept five parameters, one for each of these columns: category_id, product_code, product_name, list_price, and discount_percent. 
 
     This stored procedure should set the description column to an empty string, and it should set the date_added column to the current date.  
     
     If the value for the list_price column is a negative number, the stored procedure should raise an error that indicates that this column doesn’t accept negative numbers. Similarly, the procedure should raise an error if the value for the discount_percent column is a negative number. 

     Code at least two CALL statements that test this procedure.
     
<p align="center">
  <img src="https://user-images.githubusercontent.com/99063625/202351845-c2e8bdc4-5707-4072-a3ae-16f42a3c3c89.png">
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/99063625/202351437-f6791adc-f621-4444-8422-9e8e77bc7262.png">
</p>
     
13.  Write a script that creates and calls a stored procedure named update_product_discount that updates the discount_percent column in the Products table. This procedure should have one parameter for the product ID and another for the discount percent. 
     
     If the value for the discount_percent column is a negative number, the stored procedure should raise an error that the value for this column must be a positive number.  
     
     Code at least two CALL statements that test this procedure. 

<p align="center">
  <img src="https://user-images.githubusercontent.com/99063625/202353810-4dc77d63-b0a3-4b79-a477-0b562c093b1d.png">
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/99063625/202353977-b6c1dd43-68a1-423c-8f58-05558429f8ff.png">
</p>

### Create triggers and events 

14.  Create a trigger named products_before_update that checks the new value for the discount_percent column of the Products table. This trigger should raise an appropriate error if the discount percent is greater than 100 or less than 0. 

     If the new discount percent is between 0 and 1, this trigger should modify the new discount percent by multiplying it by 100. That way, a discount percent of .2 becomes 20. 


<p align="center">
  <img src="https://user-images.githubusercontent.com/99063625/202336232-bfbf1884-aa8c-44dc-bd5f-5c5f6a3a5618.png">
</p>

15.  Create a table named Products_Audit. This table should have all columns of the Products table, except the description column. Also, it should have an audit_id column for its primary key, and the date_added column should be changed to date_updated.  
     
     Create a trigger named products_after_update. This trigger should insert the old data about the product into the Products_Audit table after the row is updated. Then, test this trigger with an appropriate UPDATE statement. 

<p align="center">
  <img src="https://user-images.githubusercontent.com/99063625/202363882-199c95de-c14a-4970-a753-3e940357e576.png">
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/99063625/202364161-15d1515f-afd4-4fef-b932-d7e97619b8b6.png">
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/99063625/202365422-97e46a97-b7d7-4192-bee3-c94bb1f1c565.png">
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/99063625/202364454-b76cafb8-c995-4581-ae71-607aa8957c7f.png">
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/99063625/202365639-71af14d1-b3f1-415a-874d-863f8e5c6268.png">
</p>

16.  Check whether the event scheduler is turned on. If it isn’t, code a statement that turns it on.  
     
     Create an event that deletes any rows in the Products_Audit table that are older than 1 week. (You created the Products_Audit table in exercise 3.) MySQL should run this event every day. To make sure that this event has been created, code a SHOW EVENTS statement that views this event.  
   
     Once you’re sure this event is working correctly, code a DROP EVENT statement that drops the event. 

<p align="center">
  <img src="https://user-images.githubusercontent.com/99063625/202366526-0de083ea-fda9-4209-a782-019d0503eb7b.png">
</p>
