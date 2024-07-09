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

**Database 3:** `database_3`
```
-- Creating the database
 DROP DATABASE IF EXISTS `database_3`;
 CREATE DATABASE `database_3`;
 USE database_3;

-- Creating the clients table
CREATE TABLE `clients`
(
`client_id`INT(20),
`name`CHAR(50),
`address`VARCHAR(50),
`city`CHAR(30),
`state`CHAR(30),
`phone`VARCHAR(50),
PRIMARY KEY(`client_id`)
);

-- Creating the invoices table
CREATE TABLE `invoices`
(
`invoice_id`INT(10),
`number`VARCHAR(20),
`client_id`INT(10),
`invoice_total`DECIMAL(5,2),
`payment_total`DECIMAL(5,2),
`invoice_date`DATE,
`due_date`DATE,
`payment_date`DATE,
PRIMARY KEY(`invoice_id`)
);

-- Creating the payment_methods table
CREATE TABLE `payment_methods`
(
`payment_method_id`INT(20),
`name`CHAR(30),
PRIMARY KEY(`payment_method_id`)
);

-- Creating the payments table
CREATE TABLE `payments`
(
`payment_id`INT(10),
`client_id`INT(10),
`invoice_id`INT(10),
`date`DATE,
`amount`DECIMAL(5,2),
`payment_method`INT(10),
PRIMARY KEY(`payment_id`)
);
```

**Database 4:** `database_4`
```
-- Creating the database
 DROP DATABASE IF EXISTS `database_4`;
 CREATE DATABASE `database_4`;
 USE database_4;

-- Creating the customers table
CREATE TABLE `customers`
(
`customer_id`INT(20),	
`first_name`CHAR(50),	
`last_name`CHAR(50),	
`birth_date`DATE,	
`phone`VARCHAR(30),	
`address`VARCHAR(50),
`city`VARCHAR(50),	
`state`CHAR(50),
`points`INT(20),
PRIMARY KEY(`customer_id`)
);

-- Creating the order_item_notes table
CREATE TABLE `order_item_notes`
(
`note_id`INT(10),
`order_id`INT(10),
`product_id`INT(10),
`note`CHAR(30),
PRIMARY KEY(`note_id`)
);

-- Creating the order_items table
CREATE TABLE `order_items`
(
`order_id`INT(10),
`product_id`INT(10),
`quantity`INT(10),
`unit_price`DECIMAL(5,2),
PRIMARY KEY(`order_id`, `product_id`)
);

-- Creating the order_statuses table
CREATE TABLE `order_statuses`
(
`order_status_id`INT(10),
`name`CHAR(30),
PRIMARY KEY(`order_status_id`)
);

-- Creating the orders table
CREATE TABLE `orders`
(
`order_id`INT(10),
`customer_id`INT(10),
`order_date`DATE,
`status`INT(10),
`comments`VARCHAR(200),
`shipped_date`DATE,
`shipper_id`INT(10),
PRIMARY KEY(`order_id`)
);

-- Creating the products table
CREATE TABLE `products`
(
`product_id`INT(10),
`name`VARCHAR(50),
`quantity_in_stock`INT(10),
`unit_price`DECIMAL(5,2),
PRIMARY KEY(`product_id`)
);

-- Creating the shippers table
CREATE TABLE `shippers`
(
`shipper_id`INT(10),
`name`VARCHAR(50),
PRIMARY KEY(`shipper_id`)
);
```

## Data Insertion
---
The script also inserts sample data into each table for testing and demonstrating the functionality of the databases.

**Inserting Data into `database_1`:** 
```
-- Inserting data into the employees table
INSERT INTO `employees` VALUES (37270,'Yovonnda','Magrannell','Executive Secretary',63996,37270,10);
INSERT INTO `employees` VALUES (33391,'D\'arcy','Nortunen','Account Executive',62871,37270,1);
INSERT INTO `employees` VALUES (37851,'Sayer','Matterson','Statistician III',98926,37270,1);
INSERT INTO `employees` VALUES (40448,'Mindy','Crissil','Staff Scientist',94860,37270,1);
INSERT INTO `employees` VALUES (56274,'Keriann','Alloisi','VP Marketing',110150,37270,1);
INSERT INTO `employees` VALUES (63196,'Alaster','Scutchin','Assistant Professor',32179,37270,2);
INSERT INTO `employees` VALUES (67009,'North','De Clerc','VP Product Management',114257,37270,2);
INSERT INTO `employees` VALUES (67370,'Elladine','Rising','Social Worker',96767,37270,2);
INSERT INTO `employees` VALUES (68249,'Nisse','Voysey','Financial Advisor',52832,37270,2);
INSERT INTO `employees` VALUES (72540,'Guthrey','Iacopetti','Office Assistant I',117690,37270,3);
INSERT INTO `employees` VALUES (72913,'Kass','Hefferan','Computer Systems Analyst IV',96401,37270,3);
INSERT INTO `employees` VALUES (75900,'Virge','Goodrum','Information Systems Manager',54578,37270,3);
INSERT INTO `employees` VALUES (76196,'Mirilla','Janowski','Cost Accountant',119241,37270,3);
INSERT INTO `employees` VALUES (80529,'Lynde','Aronson','Junior Executive',77182,37270,4);
INSERT INTO `employees` VALUES (80679,'Mildrid','Sokale','Geologist II',67987,37270,4);
INSERT INTO `employees` VALUES (84791,'Hazel','Tarbert','General Manager',93760,37270,4);
INSERT INTO `employees` VALUES (95213,'Cole','Kesterton','Pharmacist',86119,37270,4);
INSERT INTO `employees` VALUES (96513,'Theresa','Binney','Food Chemist',47354,37270,5);
INSERT INTO `employees` VALUES (98374,'Estrellita','Daleman','Staff Accountant IV',70187,37270,5);
INSERT INTO `employees` VALUES (115357,'Ivy','Fearey','Structural Engineer',92710,37270,5);

-- Inserting data into the offices table
INSERT INTO `offices` VALUES (1,'03 Reinke Trail','Cincinnati','OH');
INSERT INTO `offices` VALUES (2,'5507 Becker Terrace','New York City','NY');
INSERT INTO `offices` VALUES (3,'54 Northland Court','Richmond','VA');
INSERT INTO `offices` VALUES (4,'08 South Crossing','Cincinnati','OH');
INSERT INTO `offices` VALUES (5,'553 Maple Drive','Minneapolis','MN');
INSERT INTO `offices` VALUES (6,'23 North Plaza','Aurora','CO');
INSERT INTO `offices` VALUES (7,'9658 Wayridge Court','Boise','ID');
INSERT INTO `offices` VALUES (8,'9 Grayhawk Trail','New York City','NY');
INSERT INTO `offices` VALUES (9,'16862 Westend Hill','Knoxville','TN');
INSERT INTO `offices` VALUES (10,'4 Bluestem Parkway','Savannah','GA');
```
