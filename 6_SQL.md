**Copyright @ Anshuman Kundu**

# SQL One short study
*by Anshuman Kundu*

### Database: It is a place where data is stored. It can be easily accessed digitally with the help of a software called DBMS (Database Management System). 

### There are two types of Databases :
1. Relational : Data is stored in a structured way in a form of a table. (MySQL, Oracle, PostgreSQL, SQL Server, etc.)
2. Non-relational: Data is stored in a randomly unstructured way and not in a form of a table. (MongoDb, etc.)
   
### SQL : Structured Query Language, used to interact with Relational Databases.

### Difference between SEQUEL and SQL : 
1. SEQUEL: Structured(S) English(E) Query(QUE) Language(L)
2. SQL: Structured(S) Query(Q) Language(L)
3. Both are similar, when this language originated it was named SEQUEL and slowly it transformed to SQL.

### What are tables, rows and columns?
1. Tables are a collection of rows and columns.
2. A column basically represents the schema/design of a table which provides the information about what all types of data the table is going to contain.
3. A row is individual data or actual data tallied to the column.

### Basic Querrying on SQL:


```sql
-- Creating and using a databse : create db_name;

create database anshuman; 
use anshuman;

-- Creating a table : create table table_name(column_name1 datatype constraint, ........);

create table projects(
	id int primary key,
    name varchar(50),
    days int not null
);


-- Insert data into the table projects: insert into table_name values (values1), (values2), ....;

insert into projects values (1, "Tripping.Trips", 30), (2, "InfoFusion", 60); 

-- Fetching all the data from the table projects: select * from table_name;

select * from projects;

-- deleting a table

drop table projects;

-- deleting a database

drop database anshuman; 

``````


