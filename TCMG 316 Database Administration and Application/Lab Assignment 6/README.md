# Lab Assignment 6

## Exercises 

We assume you have already installed MySQL server and Workbench, as well as the My Guitar Shop database with original data. In these exercises, you’ll use MySQL Workbench to perform database admin activities, including database security and backups. 

### Introduction to database administration

1. Start MySQL Workbench and open the Client Connections window. If the process list isn’t displayed, click on the Refresh button to display it. Note the number of processes in the list. Make a screen shot for the Client Connections window (2 pts). Then, return to the Home tab, open another connection for the root user, and select a different database as the current database. Next, return to the Client Connections window and refresh the process to see that it includes two additional processes for the new connection. Make another screen shot showing the new Client Connections window (2 pts).
2. In MySQL Workbench, use the Status and System Variables item from the Navigator window to view these status variables: com_select, max_used_connections, and uptime; and these system variables: basedir and datadir. In the lab report, include screen shots showing both the value and description of each of the three status variables (you must show the full descriptions); also include screen shots showing both the paths to and the description of the two system variables (you must show the full path and full descriptions). You should provide a total of 5 screen shots (1 pt each). 
3. Write and execute a SELECT statement that selects these three columns from the Customers table: email_address, first_name, last_name. Your screen shot must include full SQL syntax and the result grid (2 pts).
4. Use a SET statement to temporarily disable the general log. Then, to make sure this variable was set, use a SELECT statement to view the variable.  Your screen shot must include full SQL syntax and the result grid (2 pts). 
5. Use a SELECT statement to view the system variables that enable and disable the binary log and the error log. Your screen shot must include full SQL syntax and the result grid (2 pts).
6. Write and execute a script that creates a user with a username “mikem” and password “sesame”. This user should be able to connect to MySQL from any computer.  
 
   This user should have SELECT, INSERT, UPDATE, and DELETE privileges for the Customers, Addresses, Orders, and Order_Items tables of the My Guitar Shop database. However, this user should only have SELECT privileges for the Products and Categories tables. Also, this user should not have the right to grant privileges to other users.  

   Your screen shot should show the full SQL syntax (6 pts).
   
7. Check the privileges for user mikem by using the SHOW GRANTS statement. Your screen shot must show the full SQL syntax and the full result grid information (you should adjust the boundary of the result grid to show the full text). (2 pts) 
8. Write and execute a script that revokes the DELETE privilege on the Orders and Order_Items tables from this user. Your screen shot should show the full SQL syntax. (4 pts) 
9. Write and execute a script that changes the password expiration policy for the user mikem so the password expires immediately. Your screen shot should show the full SQL syntax. (2 pts) 
10. Write and execute a script that creates another user with a username “anneb” and password “sesame”. This user should only be able to connect from the same computer as the computer that’s running the MySQL server. Your screen shot should show the full SQL syntax. (2 pts) 
11. Write and execute a script that creates a role named clerk. The role should have the SELECT privilege for the Customers, Addresses, Orders, and Line_Items tables of the My Guitar Shop database.
    
    Assign the user anneb to the new role. 
    
    Set the default role for anneb to clerk. 
    
    Check the privileges for the role by using the SHOW GRANTS statement. 
    
    Your screenshot must show full SQL syntax, and the result grid for the SHOW GRANTS statement. (6 pts).
    
12. Start a command prompt, change to the appropriate directory and use the mysqldump program to create a full backup of the My Guitar Shop database. The backup file name should be “lab6.sql”. Your screen shot should show the full syntax of the command prompt statements. (4 pts). 
13. Open File Explorer, and navigate to the directory where you store the backup file lab6.sql. Take a screen shot of the file explore directory where lab6.sql is stored. (2 pts). 
