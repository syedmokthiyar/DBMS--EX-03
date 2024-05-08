# EX:03 Update,Delete,Select

### AIM:          
 
To Study and Implement DML Commands.

THEORY:

1. INSERT INTO: This is used to add records into a relation. 

These are three type of INSERT INTO queries which are as 

a) Inserting a single record 

Syntax:
 INSERT INTO < relation/table name> (field_1,field_2……field_n)VALUES (data_1,data_2, ...... data_n);student(sno,sname,class,address)VALUES (1,’Ravi’,’M.Tech’,’Palakol’); 

 b) Inserting all records from another relation

Syntax:
 INSERT INTO relation_name_1 SELECT Field_1,field_2,field_n FROM relation_name_2 WHERE field_x=data;

 c) Inserting multiple records 

Syntax: INSERT INTO relation_name field_1,field_2, ....field_n) VALUES (&data_1,&data_2,.......&data_n); 


2. UPDATE-SET-WHERE: 
This is used to update the content of a record in a relation. 

Syntax:
 SQL>UPDATE relation name SET Field_name1=data,field_name2=data, WHERE field_name=data; Example: SQL>UPDATE student SET sname = ‘kumar’ WHERE sno=1; 


3. DELETE-FROM: This is used to delete all the records of a relation but it will retain the structure of that relation. 

a) DELETE-FROM: This is used to delete all the records of relation. 
Syntax: DELETE FROM relation_name;

b) DELETE -FROM-WHERE: This is used to delete a selected record from a relation. 
Syntax:DELETE FROM relation_name WHERE condition; 


4)SELECT FROM: To display a set of fields for all records of relation

Syntax: 
SELECT (column1,column2) FROM (Table Name)WHERE condition;



#### 1.Write a SQL query to find customers who are either from the city 'New York' or who have a grade greater than 200. Return customer_id, cust_name, city, grade, and salesman_id.
![Screenshot 2024-05-08 105151](https://github.com/syedmokthiyar/DBMS--EX-03/assets/118787294/3b5bee2a-e508-421f-adbb-62e90298744c)
### Query:
```
SELECT customer_id, cust_name, city, grade, salesman_id
FROM customer
WHERE city = 'New York' OR grade > 200;
```
### Output:
![Screenshot 2024-05-08 105302](https://github.com/syedmokthiyar/DBMS--EX-03/assets/118787294/7e1546b7-e8f1-41c9-8c6b-b55580627321)
#### 2.write a SQL query to find customers who are either from the city 'New York' or who do not have a grade greater than 100. Return customer_id, cust_name, city, grade, and salesman_id.
![Screenshot 2024-05-08 105429](https://github.com/syedmokthiyar/DBMS--EX-03/assets/118787294/8c974188-f645-479d-adb6-41f1df1fc0f7)
### Query:
```
SELECT customer_id, cust_name, city, grade, salesman_id
FROM customer
WHERE city = 'New York' OR grade <= 100;
```
### Output:
![Screenshot 2024-05-08 105548](https://github.com/syedmokthiyar/DBMS--EX-03/assets/118787294/53cf58a6-4a19-4776-ae2a-66d93507abb8)
#### 3.Write a SQL query to locate the details of customers with grade values above 100. Return customer_id, cust_name, city, grade, and salesman_id.
![Screenshot 2024-05-08 105628](https://github.com/syedmokthiyar/DBMS--EX-03/assets/118787294/7dd834df-47c5-4bfc-8b79-09e55bae1830)
### Query:
```
SELECT customer_id, cust_name, city, grade, salesman_id
FROM customer
WHERE grade > 100;
```
### Output:
![Screenshot 2024-05-08 105728](https://github.com/syedmokthiyar/DBMS--EX-03/assets/118787294/d6352423-4e65-49d9-8138-2f2b801f4d5b)
#### 4.Write a SQL statement to retrieve city of all customers from customers table without any repeats.
![Screenshot 2024-05-08 105818](https://github.com/syedmokthiyar/DBMS--EX-03/assets/118787294/dae84a39-a1e6-4166-aa74-f2bb4321bf3e)
### Query:
```
SELECT DISTINCT city
FROM customers;
```
### Output:
![Screenshot 2024-05-08 105905](https://github.com/syedmokthiyar/DBMS--EX-03/assets/118787294/93263e23-e1cd-49ce-a505-eff1e2fcf079)

#### 5.Write a SQL statement to Increase the selling price by 15% in the products table where quantity in stock is less than 50 and supplier ID is 10.
![Screenshot 2024-05-08 105951](https://github.com/syedmokthiyar/DBMS--EX-03/assets/118787294/a12fa1be-8951-4179-ba17-bfc82d2ca856)
### Query:
```
UPDATE Products
SET sell_price = sell_price * 1.15
WHERE quantity < 50 AND supplier_id = 10;
```
### Output:
![Screenshot 2024-05-08 110118](https://github.com/syedmokthiyar/DBMS--EX-03/assets/118787294/194cde2a-69a3-422f-b31d-afab240aca34)
#### 6.Write a SQL statement to double the availability of the product with product_id 1.
![Screenshot 2024-05-08 110217](https://github.com/syedmokthiyar/DBMS--EX-03/assets/118787294/fcb738e2-b492-48d1-9d4a-4640e32fb2f5)
### Query:
```
UPDATE Products
SET availability = availability * 2
WHERE product_id = 1;
```
### Output:
![Screenshot 2024-05-08 110326](https://github.com/syedmokthiyar/DBMS--EX-03/assets/118787294/97a3ab2e-8cd6-41bd-8e81-c634772ad922)
#### 7.Write a SQL query to reduce the reorder level by 30% where cost price is more than 50 and quantity in stock is less than 100 in the products table.
![Screenshot 2024-05-08 110420](https://github.com/syedmokthiyar/DBMS--EX-03/assets/118787294/176e3745-4256-41fb-8287-bd69cc4bd8ee)
### Query:
```
UPDATE products SET reorder_lvl = reorder_lvl-(reorder_lvl * 0.3) 
WHERE cost_price > 50 AND quantity < 100;
```
### Output:
![Screenshot 2024-05-08 110550](https://github.com/syedmokthiyar/DBMS--EX-03/assets/118787294/8e857204-3b12-4579-9c54-1d7aa8e8786a)
#### 8.Write a SQL query to Delete All Doctors with a NULL Last Name
![Screenshot 2024-05-08 110633](https://github.com/syedmokthiyar/DBMS--EX-03/assets/118787294/9a2fcf4c-83e2-4a52-bf64-f7b1fcf56479)
### Query:
```
DELETE FROM Doctors
WHERE Last_Name IS NULL;
```
### Output:
![Screenshot 2024-05-08 110721](https://github.com/syedmokthiyar/DBMS--EX-03/assets/118787294/65e74f73-34bf-4da0-a8f4-ce7a59b6e1af)
#### 9.Write a SQL query to Delete customers from 'customer' table where 'CUST_CITY' is not 'New York' and 'OUTSTANDING_AMT' is greater than 5000.
![Screenshot 2024-05-08 110803](https://github.com/syedmokthiyar/DBMS--EX-03/assets/118787294/96f0bb33-1a7b-44a7-960a-476b60d1a001)
### Query:
```
DELETE FROM Customer
WHERE CUST_CITY <> 'New York' AND OUTSTANDING_AMT > 5000;
```
### Output:
![Screenshot 2024-05-08 110855](https://github.com/syedmokthiyar/DBMS--EX-03/assets/118787294/b93e39c2-101f-49f8-95dc-4fdafe861696)
#### 10.Write a SQL query to delete a doctor from Doctors table whos specialization is 'Cardiology'
![Screenshot 2024-05-08 110936](https://github.com/syedmokthiyar/DBMS--EX-03/assets/118787294/575fc0fd-00ea-4636-8b44-e6c290331df1)
### Query:
```
DELETE FROM Doctors
WHERE specialization = 'Cardiology';
```
### Output:
![Screenshot 2024-05-08 111025](https://github.com/syedmokthiyar/DBMS--EX-03/assets/118787294/16973715-8135-4af9-a0b2-ea87c0611a44)

### Result:
Therefore these are some example o implement DML Commands.
