# EXP NO 10: SYNONYMS AND ASSERTIONS IN SQL 
### DATE: 
## AIM:
To create a student database and create a synonym and assertions.

## THEORY
## SYNONYM
<div align="justify">
A SYNONYM provides another name for database object, referred to as original object, that may exist on a local or another server.
</div>
## ASSERTIONS
<div align="justify">
* An assertion is a piece of SQL which makes sure a condition is satisfied, else or it stops the action being taken on a database.
* An assertion is a constraint that might be dependent upon multiple rows of multiple tables.
</div>

## Query:
### 1) Create a table EMPLOYEE and perform insertion of two rows.

### SQL QUERY: 
CREATE TABLE EMPLOYEE (
    employee_id INT ,
    name VARCHAR(255),
    department VARCHAR(255),
    salary DECIMAL(10, 2)
);

### OUTPUT:
![image](https://github.com/lokeshkrishana/DBMS/assets/119291430/59d8edbe-857b-4a9e-85df-514b0e01e007)
![image](https://github.com/lokeshkrishana/DBMS/assets/119291430/0c9ce859-fcb2-4a49-85a0-b297913bb4e7)

### 2) Create a synonym S1 for EMPLOYEE  table.
### SQL QUERY: 
CREATE SYNONYM S1 FOR EMPLOYEE;
### OUTPUT:
![image](https://github.com/lokeshkrishana/DBMS/assets/119291430/9963d5e8-9345-480c-a302-6c32aedda7e4)
### 3) Display the EMPLOYEE  table using synonym S1.
### SQL QUERY: 
SELECT * FROM S1;
### OUTPUT:
![image](https://github.com/lokeshkrishana/DBMS/assets/119291430/f7219add-760f-4f5c-a114-a6cf3a3dbda8)
### 4) Drop the synonym.
### SQL QUERY: 
DROP SYNONYM S1;
### OUTPUT:
![image](https://github.com/lokeshkrishana/DBMS/assets/119291430/21f9c9b8-1f5d-43f1-b69f-395447ac05cc)
### 5) Create a supplier table and create a sequence S2 for supplier table id.
### SQL QUERY: 
CREATE TABLE supplier (
    id INT,
    name VARCHAR(255),
    address VARCHAR(255),
    contact_person VARCHAR(255)
);

CREATE SEQUENCE S2 START 1;

### OUTPUT:
![image](https://github.com/lokeshkrishana/DBMS/assets/119291430/6cda6c1c-1e5e-4258-8101-43c703cd7594)
![image](https://github.com/lokeshkrishana/DBMS/assets/119291430/9c1f98c6-51cd-4e7a-a9da-a0da9612177f)

### 6) insert the data into supplier table use sequence.
### SQL QUERY: 
INSERT INTO supplier (id, name, address, contact_person)
VALUES (NEXTVAL('S2'), 'ABC Suppliers', '123 Main Street', 'John Doe');

INSERT INTO supplier (id, name, address, contact_person)
VALUES (NEXTVAL('S2'), 'XYZ Distributors', '456 Elm Road', 'Jane Smith');
### OUTPUT:
![image](https://github.com/lokeshkrishana/DBMS/assets/119291430/c31223da-cfdf-4088-bb7c-775f8bb50413)
### 7) Drop the sequence

### SQL QUERY: 
DROP SEQUENCE S2;
### OUTPUT:
![image](https://github.com/lokeshkrishana/DBMS/assets/119291430/32b935fb-1d66-4280-b5f3-b67abfaf2b25)

## RESULT :
### Thus the sequence and synonym created and used in SQL.
