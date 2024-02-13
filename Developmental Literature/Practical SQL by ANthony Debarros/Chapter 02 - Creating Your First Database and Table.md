# Creating Your First Database and Table 
---
#sql #table-creation #database-creation #db #input #query-tool #pgAdmin #postgre-SQL 

- ['] SQL is more than just a means for extracting knowledge from data. It's also a language for defining the structures that hold data so we can organize relationships in their data. Chief amongst those structure are TABLES.... 
	- [i] SQL is for gleasning insights from large quantities of data 
	- [i] SQL is also used to DEFINE the DATA STRUCTURES that hold the data we use. 
	- [i] This ability to DEFINE DATA STRUCTURES allows us to control and organize the relationships in the data... 

## Understanding SQL Tables 
---
- [i] Knowing your data tables is essential to understanding the data insdie of them... Table names will hold clues about the information that lies within... But they can tell us so much more 

- [E] The number of tables will tell us how much data we will have to analyze... 
- [E] We will soon explore how we can use this introductory data to glean additional insight about the possible relational database within our data... 

- [!] When designing a database, engineers prefer to use ==Seperate Tables== for each ==main entity==... This praqctice helps to reduce the amount of redundant data within the database... 
- [!] Tables are a core building block of every single SQL database in existence... 

#### Creating A Database 
---
>[!Definition]  What Is A SQL Database?
 SQL Database is a collection of ==OBJECTS== that includes tables, functions, and much more... When you installed PostgreSQL you created a ==DATABASE SERVER==... A database server is an *instance of the application running on your computer... Our first database server omc;ided a default database called `postgres`...*

- [#] It only takes a singular line of SQL code to create a database... We can run this code by using the pgAdmin tool we prviously installed... 
- [#] The name we will give to our first database is `analysis`

```sql
CREATE DATABASE analysis;
```

- [i] Note that this code contained two important ==KEYWORDS== 
	- [ ] CREATE
	- [ ] DATABASE 

- [i] Also note the way that we ended our command... Every SQL command will get a ==SEMICOLON== to indicate the end of the code...
	- This practice is part of what is commonly known as the ==ANSI SQL STANDARD==

- [D] Some users have pointed out that certain SQL statements *COULD* work without the addition of a `;` but the fact of the matter is that many and most of them will not... In addition, the database will not give you proper indicator output on those commands, leving you guessing as to the effectiveness of what you've just input to the system... BE BY THE BOOK WITH THE ANSI SQL STANDARD!!!

#### Executing SQL in pgAdmin... 
---
- [i] When you run the SQL statements that you've written inside of `pgAdmin` this is known as `executing code`... 
- [i] It is always best practice to create a new database for each new project you begin working with... 


#### Connecting To The New `analysis` Databse 
---
>[Step  01] - Close the Query Tool by clicking the `x` at the top right corner of the given tool pane... 
- *You do NOT need to save the file when prompted*...

>[Step 02] - Inside of the browser, click `analysis` once... 

>[Step 03] - Open a new Query Tool Window, this time, you should see that you are connected to the `analysis` database... 
- `tools >>> query tool`

>[Step 04] - The label `analysis/postgres@localhost` at the top of the `Query Tool WIndow`... 

- [*] Any code executed moving forward willl be applied to the analysis database.!




#### Creating The Table Inside Of The Analysis Database...
---
- [i] A table is where your data lives... 
- [i] A table is also where all relationships it has are defined... 

- [!] Whenever you create a new table you will have to assign each and every column a ==NAME== and a ==DATATYPE==
- [!] The name you give each and every column within your database is sometimes known as a ==FIELD== or an ==ATTRIBUTE==... 

>[!Abstract] What is a DATATYPE?
>A datatype is one of the ways that SWL enforces the integrity of it's data. It's a content filter for the input data and queries... What this means is that a data column will only accept input if the data type is the same as the input, or (in other words) the data type of the input must match the datatype and parameters within the type in the column... 

#### The `CREATE TABLE` Statement
---
- [b] The next codeblock will create a table in our anlaysis database with the title teachers 

- [i] The best practice for code construction within a sql databse, is to always tab (or x4 space indent) the table data input so that the resulting code is AS HUMANLY READABLE as possible... Remember that most often in IT you will not be working alone, and will need to allow others to read your code... 

```sql
CREATE TABLE teachers (
	id bigserial,
	first_name varchar(25),
	last_name varchar(50), 
	school varchar(50),
	hire_date date,
	salary numeric
);
```

- [!] Every column within the table we just created represent 1 for 1 a ==DISCRETE DATA  ELEMENT== that is ***defined by*** a ==DATA TYPE==...

##### Digging Deeper Into The Created Table 

- [@] ==Column #1== - We have he column of `id` which is a `bigserial` datatype...
	- [ ] The `bigserial` datatype and a few other `serial` types are a Postgre specific implementation, but almost all other database systems have a similar function...

- [@] ==Column #2, #3, and #4 ==- The `first_name` and `last_name` and the `school` columns are a datatype of `varchar` which is a special datatype that has a maximum character length specified within the parenthesis that follow it... 
- [@] ==Column #5== - The `hire_date` column is a datatype of `date` which you can probably correctly assume take a date input... 
- [@] ==Column #6== - The `salary` column is a `numberic` datatype

#### Inserting Rows Into A Table
---
- [%] You are able to add data into a postgreSQL table in several ways. Most often, you'll be working with a large number of rows, so the easiest method for importing data is from a text file or another database directly into your new table... 
- [%] Since we are jsut starting with SQL, we will first add a few rows using the `INSERT INTO ... VALUES` Statement,,, 

### Using The Insert Statement... 
---
- [i] The information we will be adding into our table is input in the query table entry point that we used to create our table initially... 

```sql
INSERT INTO teachers(first_name, last_name, school, hire_date, salary)
VALUES ('Janet', 'Smith', 'F.D. Roosevelt HS', '2011-10-30', 36200),
	   ('Lee', 'Reynolds', 'F.D. Roosevelt HS', '1993-05-22', 65000), 
	   ('Samuel', 'Cole', 'Meyers Middle School', '2005-08-01', 43500), 
	   ('Samantha', 'Bush', 'Myers Middle School', '2011-10-30', 36200),
	   ('Betty', 'Diaz', 'Myers Middle School', '2005-08-30', 43500), 
	   ('Kathleen', 'Roush', 'F.D. Roosevelt HS', '2010-10-22', 38500);
```


![[Practical SQL Reference Image.png]]

- [!] Notice that in our input data, most of our column values entered were surrounded by single quotes...  Everything except for our numbers at the very end... This is because one of the `STANDARD SQL REQUIREMENTS` is that `text` and `dates` require single quotes / however, `numbers`, including both `intergers` and `decimals`  do not...
- [i] It is also helpful to recognize and commit to memory the date format of our entries in the `hire_date` column... Thia ia the `INTERNATIONAL STANDARD FOR DATE FORMAT`... It is best to just stick with this format so as to prevent confusion when dealing with databases who have hands involved from various areas around the world... 

### What About The `id` Column???
---
- [!] You may have already noticed that we did not input any sort of value for `ID` in the `id` column... This is because of the `datatype` classification we gave it upon creating the table... Due to the fact that we gave this column a datatype of `bigserial`, we will have to do no `MANUAL INSERTION` of data values... This is because the `bigserial` datatype is known as an`auto-incrementing interger`... ==AUTO INCREMENTING INTERGERS== have an automatically added value of 1, +1, +1 and so on and so forth, for every single row we create within the table,,, 

##### Viewing Our Table In pgAdmin 
---
- [i] To view the data that you just created, you simply need to go back to your pgAdmin UI and `right click the teachers table`.... Choose `View/Edit Data >>> All Rows`... As you can see, this will generate a human readable table in our UI where our input data can be viewed in the table format... 
- [I] IMPORTANT!!!! If you do input data with syntax errors while working with SQL, it will squawk back an ERROR message. The error messages received within an SQL database will look something like this... 

```sql
ERROR: syntax error at or near "("
LINE 4:         ,<sub>^</sub>('Samuel', 'Cole', 'Myers Middle School', '2005-08-01', 43...
```

- [I] If you ever receive an error message in SQL that is more obscure, than you will simply have to do what every great programmer does, which is...... READY....... WAIT FOR IT...... GOOGLE! That's right, even the most excpert of developers use google to aid them with debugging when they don't understand what an error message means.... 

## Formatting SQL For The Best Possible Readability
---
- [i] There is no required convention for the format in which you input SQL code... However, there are some best practices, that if followed early, will drastically improve the readability of your code... The formatting conventions that are best to follow are listed below... 

```sql-formatting-best-practices

SQL Keywords = UPPERCASE >>> Examples: SELECT 
DataTypes = lowercase >>> Examples: interger, text, date, bigserial

AVOID CAMEL CASE!!!! >>> Examples: DONT DO [LowercaseAndUnderscores] DO DO [lowercase_and_underscores] 

Indentation = 2 or 4 spaces OR set "tab" to 4 spaces >>> EXAMPLE SHOWN BELOW 

DO		INSERT INTO [tablename] (column1, column2, column3), 
		VALUES (`Input`, 'Input', 'input'),
			 ('Input', 'Input', 'Input'),  

DONT		INSERT INTO [tablename] (column1, column2, column3), 
		VALUES (`Input`, 'Input', 'input'),
		('Input', 'Input', 'Input'),  
```

- [i] There are planty more SQL coding conventions, so pay close attention to patterns you see form as we move forward.... 
















