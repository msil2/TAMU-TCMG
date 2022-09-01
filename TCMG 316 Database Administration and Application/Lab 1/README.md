# Lab Assignment 1

## Before you start the exercise...

* Install the MySQL server and MySQL WOrkbench.
* Download and extract the mgs_ex_starts directory. This directory contains some script files that you need to do the exercises in this and subsequent labs.

## Exercises

In these exercises, you’ll use MySQL Workbench to create the My Guitar Shop database, to review the tables in this database, and to enter SQL statements and run them against this database.

### Make sure the MySQL server is running.

<img width="943" alt="MySQL_Lab1_1" src="https://user-images.githubusercontent.com/99063625/188025439-b48134df-d051-4602-8d94-841da0ef1e5f.png">

Click on "Server" in the file menu bar, then "Server Status."

### Use MySQL Workbench to create the My Guitar Shop database.

<img width="1106" alt="MySQL_Lab1_2" src="https://user-images.githubusercontent.com/99063625/188025994-cabeee24-0b6a-4a4c-93c3-6d2856a96997.png">

Execute the 'create_my_guitar_shop.sql' script.

### Use MySQL Workbench to review the My Guitar Shop database.

<img width="900" alt="MySQL_Lab1_3" src="https://user-images.githubusercontent.com/99063625/188026253-3caa2669-9af4-422e-a0cc-12d7b4981de8.png">

View the data for the 'products' table.

![image](https://user-images.githubusercontent.com/99063625/188026560-ce08f53f-de09-4e60-9f8d-b55a56eff603.png)

View the column definitions for the 'customers' table.

### Use MySQL WOrkbench to enter and run SQL statements.

![image](https://user-images.githubusercontent.com/99063625/188027552-dc09bd40-d7b2-4b98-a2d9-2dd93d23bb8e.png)

Set 'my_guitar_shop' database as the default database, then select data from the database.

![image](https://user-images.githubusercontent.com/99063625/188028024-9cc2908f-c2d5-4749-ad51-733b371adf7a.png)
![image](https://user-images.githubusercontent.com/99063625/188028075-a9aa6eaf-718c-4ba2-b469-e0b7214a62f5.png)

Delete the *e* at the end of 'product_name' and run the statement again to get *Error Code: 1054. Unknown column 'product_nam' in 'field list'.*

![image](https://user-images.githubusercontent.com/99063625/188028590-adeffcc7-404e-4a46-9dc9-ca7dd941689e.png)

Return the number of products (rows) in the 'products' table.

### Use MySQL Workbench to open and run scripts.

![image](https://user-images.githubusercontent.com/99063625/188028889-8a870463-1456-44bf-aca8-5dbebf5cf31a.png)

Execute 'product_details.sql' script.

