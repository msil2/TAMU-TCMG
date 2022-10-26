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

