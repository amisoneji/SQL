- **syntax of create table:**

    create table table_name(col_name datatype,col_name datatype,......)

- **syntax of desc table:**

   desc table_name

- **syntax to add a column in existing table:**

   alter table table_name add col_name datatype

- **syntax to modify a column datatype in existing table:**

   alter table table_name modify column col_name datatype

- **syntax to drop a column in existing table:**

   alter table table_name drop column col_name 

- **syntax to rename a table:**

   alter table old_table_name rename to new_table_name

- **syntax to rename column in existing table:**

   alter table table_name change column old_col_name new_col_name datatype

- **syntax to drop(delete) table:**

   drop table table_name


- **syntax to insert a record/row:**

   insert into table_name values(col1_value,col2_value,......)

- **syntax to insert a record/row according to custom order of columns:**

   insert into table_name(col1,col2,....) values(col1_value,col2_value,......)


- **The SQL SELECT DISTINCT Statement:**

   SELECT DISTINCT column1, column2, ...FROM table_name;


- **The SQL WHERE Clause:**

   The WHERE clause is used to extract only those records that fulfill a specified condition.

   SELECT column1, column2, ...FROM table_name WHERE condition;

- **Operator	Description**	

          =		     Equal	

          >		     Greater than	

          <		     Less than	

          >=	     Greater than or equal	

          <=	     Less than or equal	
 
          !=		   Not equal. Note: In some versions of SQL this operator may be written as <>	

          BETWEEN	Between a certain range	

          LIKE		Search for a pattern	
   
          IN		  To specify multiple possible values for a column


- **The SQL LIKE Operator:**

   > The LIKE operator is used in a WHERE clause to search for a specified pattern in a column.

   > There are two wildcards often used in conjunction with the LIKE operator:

      % - The percent sign represents zero, one, or multiple characters
    

      _ - The underscore represents a single character


          LIKE Operator				                  Description

          WHERE CustomerName LIKE 'a%'	       Finds any values that start with "a"

          WHERE CustomerName LIKE '%a'	       Finds any values that end with "a"
 
          WHERE CustomerName LIKE '%a%'	       Finds any values that have "a" in any position

          WHERE CustomerName LIKE '_r%'	       Finds any values that have "r" in the second position

          WHERE CustomerName LIKE 'a_%'       Finds any values that start with "a" and are at least 2 characters in length

          WHERE CustomerName LIKE 'a__%'	    Finds any values that start with "a" and are at least 3 characters in length

          WHERE ContactName LIKE 'a%o'	      Finds any values that start with "a" and ends with "o"

**The SQL IN Operator:**

-  The IN operator allows you to specify multiple values in a WHERE clause.

-  The IN operator is a shorthand for multiple OR conditions.

 - SELECT column_name(s) FROM table_name WHERE column_name IN (value1, value2, ...);


