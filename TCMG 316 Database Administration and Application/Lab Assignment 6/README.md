# Lab Assignment 6

## Exercises 

We assume you have already installed MySQL server and Workbench, as well as the My Guitar Shop database with original data. In these exercises, you’ll use MySQL Workbench to perform database admin activities, including database security and backups. 

### Introduction to database administration

1. Start MySQL Workbench and open the Client Connections window. If the process list isn’t displayed, click on the Refresh button to display it. Note the number of processes in the list. Make a screen shot for the Client Connections window (2 pts). Then, return to the Home tab, open another connection for the root user, and select a different database as the current database. Next, return to the Client Connections window and refresh the process to see that it includes two additional processes for the new connection. Make another screen shot showing the new Client Connections window (2 pts).

<p align="center">
  <img src="https://user-images.githubusercontent.com/99063625/204127088-6e990900-07b5-4a64-8899-8261cd65ef9b.png">
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/99063625/204127356-c7719e2c-32fe-45c0-b251-e278ca794f93.png">
</p>

2. In MySQL Workbench, use the Status and System Variables item from the Navigator window to view these status variables: com_select, max_used_connections, and uptime; and these system variables: basedir and datadir. In the lab report, include screen shots showing both the value and description of each of the three status variables (you must show the full descriptions); also include screen shots showing both the paths to and the description of the two system variables (you must show the full path and full descriptions). You should provide a total of 5 screen shots (1 pt each). 

<p align="center">
  <img src="https://user-images.githubusercontent.com/99063625/204127599-1de9754d-5955-4d3d-ba65-1314b441f2b3.png">
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/99063625/204127633-4d5494ee-9e8d-4e7f-89bc-8fca8d3b7621.png">
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/99063625/204127649-76132343-2e15-46d6-9917-f427eb006051.png">
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/99063625/204127673-8855ff5e-ab42-4f66-b93c-1e50ca608842.png">
</p>
<p align="center">
  <img src="https://user-images.githubusercontent.com/99063625/204127700-ff0cc3ba-8d80-4756-86c1-afe6e2668c94.png">
</p>

3. Write and execute a SELECT statement that selects these three columns from the Customers table: email_address, first_name, last_name. Your screen shot must include full SQL syntax and the result grid (2 pts).

<p align="center">
  <img src="https://user-images.githubusercontent.com/99063625/204127963-3a221d63-b7c1-4af4-9a58-8393bcfaa657.png">
</p>

4. Use a SET statement to temporarily disable the general log. Then, to make sure this variable was set, use a SELECT statement to view the variable.  Your screen shot must include full SQL syntax and the result grid (2 pts). 

<p align="center">
  <img src="https://user-images.githubusercontent.com/99063625/204128100-8c78c58a-c68b-4e31-8d63-9dc873fedba1.png">
</p>

5. Use a SELECT statement to view the system variables that enable and disable the binary log and the error log. Your screen shot must include full SQL syntax and the result grid (2 pts).

<p align="center">
  <img src="https://user-images.githubusercontent.com/99063625/204889568-04ed6490-766d-479a-b7d8-967a83010920.png">
</p>

### Database security

6. Write and execute a script that creates a user with a username “mikem” and password “sesame”. This user should be able to connect to MySQL from any computer.  
 
   This user should have SELECT, INSERT, UPDATE, and DELETE privileges for the Customers, Addresses, Orders, and Order_Items tables of the My Guitar Shop database. However, this user should only have SELECT privileges for the Products and Categories tables. Also, this user should not have the right to grant privileges to other users.  

   Your screen shot should show the full SQL syntax (6 pts).

   <p align="center">
     <img src="https://user-images.githubusercontent.com/99063625/204951537-88326d57-91db-4336-a3fd-96c795b2e171.png">
   </p>
   
7. Check the privileges for user mikem by using the SHOW GRANTS statement. Your screen shot must show the full SQL syntax and the full result grid information (you should adjust the boundary of the result grid to show the full text). (2 pts) 

<p align="center">
  <img src="https://user-images.githubusercontent.com/99063625/204948001-d015577f-c6aa-452a-bbba-db82b9790516.png">
</p>

8. Write and execute a script that revokes the DELETE privilege on the Orders and Order_Items tables from this user. Your screen shot should show the full SQL syntax. (4 pts) 

<p align="center">
  <img src="https://user-images.githubusercontent.com/99063625/204948568-48fc83f7-f773-4fde-a7e8-f1edf79d314a.png">
</p>

9. Write and execute a script that changes the password expiration policy for the user mikem so the password expires immediately. Your screen shot should show the full SQL syntax. (2 pts)  

<p align="center">
  <img src="https://user-images.githubusercontent.com/99063625/204950357-72436719-bc04-4a51-9a43-2eedccfd172b.png">
</p>

10. Write and execute a script that creates another user with a username “anneb” and password “sesame”. This user should only be able to connect from the same computer as the computer that’s running the MySQL server. Your screen shot should show the full SQL syntax. (2 pts) 

<p align="center">
  <img src="https://user-images.githubusercontent.com/99063625/204952595-71129211-8992-4aef-96d1-4b6992db7677.png">
</p>

11. Write and execute a script that creates a role named clerk. The role should have the SELECT privilege for the Customers, Addresses, Orders, and Line_Items tables of the My Guitar Shop database.
    
    Assign the user anneb to the new role. 
    
    Set the default role for anneb to clerk. 
    
    Check the privileges for the role by using the SHOW GRANTS statement. 
    
    Your screenshot must show full SQL syntax, and the result grid for the SHOW GRANTS statement. (6 pts).
    
### Database backup    
    
12. Start a command prompt, change to the appropriate directory and use the mysqldump program to create a full backup of the My Guitar Shop database. The backup file name should be “lab6.sql”. Your screen shot should show the full syntax of the command prompt statements. (4 pts). 
13. Open File Explorer, and navigate to the directory where you store the backup file lab6.sql. Take a screen shot of the file explore directory where lab6.sql is stored. (2 pts). 
