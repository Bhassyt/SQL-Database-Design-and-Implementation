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

**Inserting Data into `database_2`:** 
```
-- Inserting data into the products table
INSERT INTO `products` VALUES (1,'Foam Dinner Plate',70,1.21);
INSERT INTO `products` VALUES (2,'Pork - Bacon,back Peameal',49,4.65);
INSERT INTO `products` VALUES (3,'Lettuce - Romaine, Heart',38,3.35);
INSERT INTO `products` VALUES (4,'Brocolinni - Gaylan, Chinese',90,4.53);
INSERT INTO `products` VALUES (5,'Sauce - Ranch Dressing',94,1.63);
INSERT INTO `products` VALUES (6,'Petit Baguette',14,2.39);
INSERT INTO `products` VALUES (7,'Sweet Pea Sprouts',98,3.29);
INSERT INTO `products` VALUES (8,'Island Oasis - Raspberry',26,0.74);
INSERT INTO `products` VALUES (9,'Longan',67,2.26);
INSERT INTO `products` VALUES (10,'Broom - Push',6,1.09);
```

**Inserting Data into `database_3`:** 
```
-- Inserting data into the clients table
INSERT INTO `clients` VALUES (1,'Vinte','3 Nevada Parkway','Syracuse','NY','315-252-7305'); 
INSERT INTO `clients` VALUES (2,'Myworks','34267 Glendale Parkway','Huntington','WV','304-659-1170'); 
INSERT INTO `clients` VALUES (3,'Yadel','096 Pawling Parkway','San Francisco','CA','415-144-6037'); 
INSERT INTO `clients` VALUES (4,'Kwideo','81674 Westerfield Circle','waco','TX','254-750-0784'); 
INSERT INTO `clients` VALUES (5,'Topiclounge','0863 Farmco Road','Portland','OR','971-888-9129'); 

-- Inserting data into the invoices table
INSERT INTO `invoices` VALUES (	1,'91-953-3396',2,101.79,0.00,'2019-03-09','2019-03-29',NULL); 
INSERT INTO `invoices` VALUES (2,'03-898-6735',5,175.32,8.18,'2019-06-11','2019-07-01','2019-02-12');
INSERT INTO `invoices` VALUES (3,'20-228-0335',5,147.99,0.00,'2019-07-31','2019-08-20',NULL);
INSERT INTO `invoices` VALUES (4,'56-934-0748',3,152.21,0.00,'2019-03-08','2019-03-28',NULL);
INSERT INTO `invoices` VALUES (5,'87-052-3121',5,169.36,0.00,'2019-07-18','2019-08-07',NULL);
INSERT INTO `invoices` VALUES (6,'75-587-6626',1,157.78,74.55,'2019-01-29','2019-02-18','2019-01-03');
INSERT INTO `invoices` VALUES (7,'68-093-9863',3,133.87,0.00,'2019-09-04','2019-09-24',NULL);
INSERT INTO `invoices` VALUES (8,'78-145-1093',1,189.12,0.00,'2019-05-20','2019-06-09',NULL);
INSERT INTO `invoices` VALUES (9,'77-593-0081',5,172.17,0.00,'2019-07-09','2019-07-29',NULL);
INSERT INTO `invoices` VALUES (10,'48-266-1517',1,159.50,0.00,'2019-06-30','2019-07-20',NULL);
INSERT INTO `invoices` VALUES (11,'20-848-0181',3,126.15,0.03,'2019-01-07','2019-01-27','2019-01-11');
INSERT INTO `invoices` VALUES (13,'41-666-1035',5,135.01,87.44,'2019-06-25','2019-07-15','2019-01-26');
INSERT INTO `invoices` VALUES (15,'55-105-9605',3,167.29,80.31,'2019-11-25','2019-12-15','2019-01-15');
INSERT INTO `invoices` VALUES (16,'10-451-8824',1,162.02,0.00,'2019-03-30','2019-04-19',NULL);
INSERT INTO `invoices` VALUES (17,'33-615-4694',3,126.38,68.10,'2019-07-30','2019-08-19','2019-01-15');
INSERT INTO `invoices` VALUES (18,'52-269-9803',5,180.17,42.77,'2019-05-23','2019-06-12','2019-01-08');
INSERT INTO `invoices` VALUES (19,'83-559-4105',1,134.47,0.00,'2019-11-23','2019-12-13',NULL);

-- Inserting data into the payment_methods table
INSERT INTO `payment_methods` VALUES (1, `Credit Card`);
INSERT INTO `payment_methods` VALUES (2, `Cash`);
INSERT INTO `payment_methods` VALUES (3, `PayPal`);
INSERT INTO `payment_methods` VALUES (4, `Wire Transfer`);

-- Inserting data into the payments table
INSERT INTO `payments` VALUES (1,5,2,'2019-02-12',8.18,1);
INSERT INTO `payments` VALUES (2,1,6,'2019-01-03',74.55,1);
INSERT INTO `payments` VALUES (3,3,11,'2019-01-11',0.03,1);
INSERT INTO `payments` VALUES (4,5,13,'2019-01-26',87.44,1);
INSERT INTO `payments` VALUES (5,3,15,'2019-01-15',80.31,1);
INSERT INTO `payments` VALUES (6,3,17,'2019-01-15',68.10,1);
INSERT INTO `payments` VALUES (7,5,18,'2019-01-08',32.77,1);
INSERT INTO `payments` VALUES (8,5,18,'2019-01-08',10.00,2);

-- Inserting data into the payments table
