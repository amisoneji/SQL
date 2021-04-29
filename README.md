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

- **The SQL IN Operator:**

   > The IN operator allows you to specify multiple values in a WHERE clause.

   > The IN operator is a shorthand for multiple OR conditions.

   > SELECT column_name(s) FROM table_name WHERE column_name IN (value1, value2, ...);

- **The SQL AND, OR and NOT Operators:**

   > The AND and OR operators are used to filter records based on more than one condition:

   > The AND operator displays a record if all the conditions separated by AND are TRUE.

   > The OR operator displays a record if any of the conditions separated by OR is TRUE.

   > The NOT operator displays a record if the condition(s) is NOT TRUE.

- **The SQL ORDER BY Keyword:**

   > The ORDER BY keyword sorts the records in ascending order by default. To sort the records in descending order, use the DESC keyword.

   > SELECT column1, column2, ...FROM table_name ORDER BY column1, column2, ... ASC|DESC;
   
- **The SQL UPDATE Statement:**

   > The UPDATE statement is used to modify the existing records in a table.

   > UPDATE table_name SET column1 = value1, column2 = value2, ...WHERE condition;


- **The SQL DELETE Statement:**

   > The DELETE statement is used to delete existing records in a table.

   > DELETE FROM table_name WHERE condition;

- **How to find missing/NULL values in a column:**

    > select * from table_name where col_name is null;


**SQL Constraints:**
_________________________________________________________________________________________________________________________________

- SQL constraints are used to specify rules for the data in a table.

- Constraints are used to limit the type of data that can go into a table.

- Constraints can be column level or table level. 

- Column level constraints apply to a column, and table level constraints apply to the whole table.

**The following constraints are commonly used in SQL:**

- NOT NULL - Ensures that a column cannot have a NULL value
- UNIQUE - Ensures that all values in a column are different
- PRIMARY KEY - A combination of a NOT NULL and UNIQUE. Uniquely identifies each row in a table
- FOREIGN KEY - Uniquely identifies a row/record in another table
- CHECK - Ensures that all values in a column satisfies a specific condition
- DEFAULT - Sets a default value for a column when no value is specified

**SQL NOT NULL Constraint:**

  By default, a column can hold NULL values.

  The NOT NULL constraint enforces a column to NOT accept NULL values.

  syntax:

  create table table_name(col_name datatype NOT NULL,......)

  ALTER TABLE table_name MODIFY col_name datatype NOT NULL;

**SQL UNIQUE Constraint:**

  The UNIQUE constraint ensures that all values in a column are different.

  syntax:

  create table table_name(col_name datatype unique,......)

  ALTER TABLE table_name add unique(col_name)

**SQL PRIMARY KEY Constraint:**

  The PRIMARY KEY constraint uniquely identifies each record in a table.

  Primary keys must contain UNIQUE values, and cannot contain NULL values.

  A table can have only ONE primary key; and in the table, this primary key can consist of single or multiple columns (fields).

  syntyax:

  create table table_name(col_name datatype PRIMARY KEY,col_name datatype,......)
                                     or
  create table table_name(col_name datatype,col_name datatype,......,PRIMARY KEY(col_name))

  ALTER TABLE table_name ADD PRIMARY KEY (col_name);

  ALTER TABLE table_name DROP PRIMARY KEY;

**SQL COMPOSITE KEY:**

  A composite key is a combination of two or more columns in a table that can be used to uniquely

  Identify each row in the table when the columns are combined uniqueness is guaranteed, but when it taken individually it does not       guarantee uniqueness.

  syntax:

  create table table_name(col_name1 datatype,col_name2 datatype,......,PRIMARY KEY(COL1,COL2,..))


**SQL FOREIGN KEY Constraint:**

  A FOREIGN KEY is a key used to link two tables together.

  A FOREIGN KEY is a field (or collection of fields) in one table that refers to the PRIMARY KEY in another table.

  The table containing the foreign key is called the child table, and the table containing the primary key is called the referenced or     parent table. 

  The FOREIGN KEY constraint also prevents invalid data from being inserted into the foreign key column, because it has to be one of the   values contained in the table it points to.

  syntax:
  create table table_name1(col_name1 datatype,col_name2 datatype,......,PRIMARY KEY(COL))

  create table table_name2(col_name1 datatype,col_name2 datatype,......,FOREIGN KEY(COL) 
  
  REFERENCES table_name1(pk_col_table1))

**SQL CHECK Constraint:**
  
  The CHECK constraint is used to limit the value range that can be placed in a column.

  If you define a CHECK constraint on a single column it allows only certain values for this column.

  If you define a CHECK constraint on a table it can limit the values in certain columns based on values in other columns in the row.

  The following SQL creates a CHECK constraint on the "Age" column when the "Persons" table is created.

  The CHECK constraint ensures that the age of a person must be 18, or older:

  syntax:

     CREATE TABLE Persons (
        
        ID int NOT NULL,
        
        LastName varchar(255) NOT NULL,
        
        FirstName varchar(255),
        
        Age int,
        
        CHECK (Age>=18)
       
       );

  To allow naming of a CHECK constraint, and for defining a CHECK constraint on multiple columns, use the following SQL syntax:

    CREATE TABLE Persons (
       
       ID int NOT NULL,
       
       LastName varchar(255) NOT NULL,
       
       FirstName varchar(255),
       
       Age int,
      
      City varchar(255),
      
      CONSTRAINT CHECK (Age>=18 AND City='Sandnes')
     
     );

 The DEFAULT constraint is used to provide a default value for a column.
 
 The default value will be added to all new records IF no other value is specified.
 
 The following SQL sets a DEFAULT value for the "City" column when the "Persons" table is created:

   CREATE TABLE Persons (
     
         ID int NOT NULL,
         
         LastName varchar(255) NOT NULL,
         
         FirstName varchar(255),
     
         Age int,
         
         City varchar(255) DEFAULT 'Noida'
  );

 The DEFAULT constraint can also be used to insert system values, by using functions like GETDATE():

     CREATE TABLE Orders (
           
           ID int NOT NULL,
          
           OrderNumber int NOT NULL,
     
           OrderDate date DEFAULT GETDATE()
           
           );
           
**AUTO INCREMENT Field:**

   Auto-increment allows a unique number to be generated automatically when a new record is inserted into a table.

   Often this is the primary key field that we would like to be created automatically every time a new record is inserted.

   Syntax for MySQL

   The following SQL statement defines the "Personid" column to be an auto-increment primary key field in the "Persons" table:

   CREATE TABLE Persons (
       Personid int NOT NULL AUTO_INCREMENT,
       
       LastName varchar(255) NOT NULL,
       
       FirstName varchar(255),
       
       Age int,
    
       PRIMARY KEY (Personid)
       
       );
   
   By default, the starting value for AUTO_INCREMENT is 1, and it will increment by 1 for each new record.
   
   To let the AUTO_INCREMENT sequence start with another value, use the following SQL statement:
   
   ALTER TABLE Persons AUTO_INCREMENT=100;


**MySQL Functions:**
________________________________________________________________________________________________________________________________

   MySQL has many built-in functions.

   Commonly Used String Functions:

      Function		        Description

      CHAR_LENGTH	       Returns the length of a string (in characters)
   
      CONCAT		       Adds two or more expressions together

      LOWER		           Converts a string to lower-case
   
      REVERSE		       Reverses a string and returns the result
   
      UPPER		           Converts a string to upper-case


**Commonly Used Numeric Functions:**

     Function		Description
  
     ABS		    Returns the absolute value of a number
  
     AVG		    Returns the average value of an expression
  
     CEIL		    Returns the smallest integer value that is >= to a number
  
     COUNT		    Returns the number of records returned by a select query
 
     FLOOR		    Returns the largest integer value that is <= to a number
  
     MAX		    Returns the maximum value in a set of values
  
     MIN		    Returns the minimum value in a set of values
  
     SUM		    Calculates the sum of a set of values

**Commonly Date Functions:**

    Function	   Description
 
    CURDATE		   Returns the current date

    CURTIME		   Returns the current time

    NOW		       Returns the current date and time














