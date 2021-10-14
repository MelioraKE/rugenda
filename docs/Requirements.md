
# How to use the tool

## Use Case 1: Connect to a remote DB and execute Queries

+ Step 1: Checking the properties:
    + Check if there is a db.properties file
        + first check if there is a specified dbconfigs file using -Ddbconfigs
        + if no file is specified, print a message that the user requires to save a db configs on root folder...
        + 
    + Check if -D arguments override for the following:
        + -Durl=jdbc:oracle:thin:@localhost:1521:xe
        + -Dusername=system
        + -Dpassword=password
    + In case of -D arguments, we need to override the values from db.properties

    + We need to print the db connection information on console, mask the password as we print
    
+ Step 2: Connect to the database
  + Use the database connection detais provided in step 1 above to open a database connection 
    + In case we have connection issue, please print the error on console
    + In case of successful connection, print connection successful message
    
+ Step 3: Provide a user prompt to enter a query 
  + The system should allow the user to type in a query to be executed 
  + If a query has data modification keywords (e.g. INSERT, ALTER, UPDATE, DELETE ) we will execute the query 
  + Else we should executeQuery - expecting a result set to be returned 
  + There should be a way to pass a query on command line
    + e.g. -Dq="select * from tbl_users" 
    + e.g. OR -Dquery="select * from tbl_users"
    + In such a case, no need for the user prompt
    
  + Once the query is excuted, we should print result
    + In case of an execute - we need to print success or failure reason 
    + In case of executeQuery 
      + We need to print the rows returned in case of a result set 
      + We neeed to print error message in case of an issue 
  
  + In the command line util, the following requirements need to be support:
    + An empty input (hitting enter) should not lead to empty query being executed
    + To quit, the user can type 'quit' or 'bye' to end the terminal session 
    + A command to executed can be optionally terminated with a semicolon (;) 
    + In case two queries are seperated by a semicolon, then system should proceed and execute the two queries


## Use Case 2: Data migration tool

To be specified later 
