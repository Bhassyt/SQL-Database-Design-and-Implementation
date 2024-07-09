# SQL-Database-Design-and-Implementation
---

**Documentation Outlines**

- [Project Overview](#project-overview)
- [Database and Table Creation](#database-and-table-creation)
- [Data Insertion](#data-insertion)
- [Execution Results](#execution-results)
- [Conclusion](#conclusion)

## Project Overview
---
This SQL script demonstrates my ability to design and implement relational databases. The script creates and populates four distinct databases, each designed to manage different types of data and relationships. Each database includes several tables with appropriate data types and primary keys to ensure data integrity and efficient querying.

## Database and Table creation
---
The first part of the script creates the databases and their respective tables.

**Database 1:** `database_1`
```
-- Creating the database
DROP DATABASE IF EXISTS `database_1`;
CREATE DATABASE `database_1`;
USE database_1;

-- Creating the employees table
CREATE TABLE `employees`
(
`employee_id`INT(10) NOT NULL,
 `first_name`CHAR(50) NOT NULL,
 `last_name`CHAR(50) NOT NULL,
 `job_title`CHAR(50) NOT NULL,
 `salary`INT(20) NOT NULL,
 `report_to`INT(10) NOT NULL,
 `office_id`INT(10) NOT NULL, 
 PRIMARY KEY(`employee_id`)
 );

-- Creating the offices table
 CREATE TABLE `offices`
 (
 `office_id`INT(10) NOT NULL,
 `address`VARCHAR(50) NOT NULL,
 `city`CHAR(30) NOT NULL,
 `state`CHAR(30) NOT NULL,
 PRIMARY KEY(`office_id`)
 );
```

**Database 2:** `database_2`
```
-- Creating the database
 DROP DATABASE IF EXISTS `database_2`;
 CREATE DATABASE `database_2`;
 USE database_2;

-- Creating the products table
 CREATE TABLE `products`
 (
 `product_id`INT(20),
 `name`VARCHAR(50),
 `quantity_in_stock`INT(20),
 `unit_price`DECIMAL(5,2),
 PRIMARY KEY(`product_id`)
 );
```
