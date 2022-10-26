# Lab Assignment 3
 
## Exercises 
 
We assume you have already installed MySQL server and Workbench, as well as the My Guitar Shop database with original data. In these exercises, you’ll use MySQL Workbench to create new database and views, and work on the My Guitar Shop database. 
 
### How to create databases, tables, and indexes 

1. Write a script that adds an index to the my_guitar_shop database for the order_date field in the Orders table. (2 pts)  
 
   ![image](https://user-images.githubusercontent.com/99063625/198109007-41bbf198-0af0-4250-98e0-9dd16f27aa02.png)
 
2. Write a script that implements the following design in a database named my_web_db (7 pts):

   ![image](https://user-images.githubusercontent.com/99063625/198109272-59880881-cc62-47d4-977e-8dca3bdc9ab8.png)

   In the Downloads table, the user_id and product_id columns are the foreign keys.  
   Include a statement to drop the database if it already exists.  
   Include statements to create and select the database.  
   Include any indexes that you think are necessary.  
   Specify the utf8mb4 character set for all tables.  
   Specify the InnoDB storage engine for all tables.

   ![image](https://user-images.githubusercontent.com/99063625/198112487-3a8c70ee-fd49-4f3a-a0db-a7c767a3bc3d.png)

3. Write a script that adds the following rows to the database that you created in exercise 2.

   - Add two rows to the Users and Products tables with the following data (2 pts): 
     - Users: (1, johnsmith@gmail.com, John, Smith) and (2, janedoe@yahoo.com, Jane, Doe) 
     - Products: (1, Local Music Vol 1) and (2, Local Music Vol 2)  
   - Add three rows to the Downloads table (2 pts): one row for user 1 and product 2; one row for user 2 and product 1; and one row for user 2 and product 2. Use the NOW function to insert the  current date and time into the download_date column. Make up your own filenames for the  filename column.
   - Write a SELECT statement that joins the three tables and retrieves the data from these tables like this (3 pts): 
  
     ![image](https://user-images.githubusercontent.com/99063625/198121177-9ecd30f2-4017-403d-9a8c-080c4115e1ae.png)
  
     Sort the result set by the email address in descending sequence and the product name in ascending sequence.
  
     ![image](https://user-images.githubusercontent.com/99063625/198122899-a226e5b9-4dca-4248-9df2-b71d1e82aa38.png)

4. Write an ALTER TABLE statement that adds the following two new columns to the Products table created in exercise 2.  

   - Add one column for product price that provides for three digits to the left of the decimal point and two to the right. This column should have a default value of 9.99 (2 pts). 
   - Add one column for the date and time that the product was added to the database (2 pts). 

   ![image](https://user-images.githubusercontent.com/99063625/198127344-fbb31ba3-927c-45bd-80e4-f2781a8cdde7.png)

5. Modify the tables created in exercise 2 in the following ways. 

   - Write an ALTER TABLE statement that modifies the Users table so the first_name column cannot store NULL values and can store a maximum of 20 characters (2 pts).  
   - Code an UPDATE statement that attempts to insert a NULL value into this column for user 1. It should fail due to the NOT NULL constraint (2 pts). 
   - Code another UPDATE statement that attempts to insert a first name that’s longer than 20 characters for user 1. It should fail due to the length of the column (2 pts).

   ![image](https://user-images.githubusercontent.com/99063625/198136359-e23a8558-9d91-4ef9-b4cb-6e7e471cad80.png)
