
# EXP NO 5: SubQueries, Views and Joins 

### DATE : 13/09/23

## AIM
### To use SubQueries, Views and Joins in SQL 


## Create employee Table
```sql
CREATE TABLE EMP (EMPNO NUMBER(4) PRIMARY KEY,ENAME VARCHAR2(10),JOB VARCHAR2(9),MGR NUMBER(4),HIREDATE DATE,SAL NUMBER(7,2),COMM NUMBER(7,2),DEPTNO NUMBER(2));
```


## Insert the values
```sql
INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7369, 'SMITH', 'CLERK', 7902, '17-DEC-80', 800, NULL, 20);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7499, 'ALLEN', 'SALESMAN', 7698, '20-FEB-81', 1600, 300, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7521, 'WARD', 'SALESMAN', 7698, '22-FEB-81', 1250, 500, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7566, 'JONES', 'MANAGER', 7839, '02-APR-81', 2975, NULL, 20);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7654, 'MARTIN', 'SALESMAN', 7698, '28-SEP-81', 1250, 1400, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7698, 'BLAKE', 'MANAGER', 7839, '01-MAY-81', 2850, NULL, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7782, 'CLARK', 'MANAGER', 7839, '09-JUN-81', 2450, NULL, 10);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7788, 'SCOTT', 'ANALYST', 7566, '19-APR-87', 3000, NULL, 20);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7839, 'KING', 'PRESIDENT', NULL, '17-NOV-81', 5000, NULL, 10);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7844, 'TURNER', 'SALESMAN', 7698, '08-SEP-81', 1500, 0, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7876, 'ADAMS', 'CLERK', 7788, '23-MAY-87', 1100, NULL, 20);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7900, 'JAMES', 'CLERK', 7698, '03-DEC-81', 950, NULL, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7902, 'FORD', 'ANALYST', 7566, TO_DATE('03-DEC-81', 'DD-MON-RR'), 3000, 20, 20);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7934, 'MILLER', 'CLERK', 7782, TO_DATE('23-JAN-82', 'DD-MON-RR'), 1300, 10, 10);
```


## Create department table
```sql
CREATE TABLE DEPT (DEPTNO NUMBER(2) PRIMARY KEY,DNAME VARCHAR2(14),LOC VARCHAR2(13));
```


## Insert the values in the department table
```sql
INSERT INTO DEPT (DEPTNO, DNAME, LOC) VALUES (10, 'ACCOUNTING', 'NEW YORK');

INSERT INTO DEPT (DEPTNO, DNAME, LOC) VALUES (20, 'RESEARCH', 'DALLAS');

INSERT INTO DEPT (DEPTNO, DNAME, LOC) VALUES (30, 'SALES', 'CHICAGO');

INSERT INTO DEPT (DEPTNO, DNAME, LOC) VALUES (40, 'OPERATIONS', 'BOSTON');
```


### Q1) List the name of the employees whose salary is greater than that of employee with empno 7566.


### QUERY:
![image](https://github.com/lokeshkrishana/DBMS/assets/119291430/65cb4b8a-cdae-432f-bd04-3ea51309a509)




### OUTPUT:
![image](https://github.com/lokeshkrishana/DBMS/assets/119291430/24faa4fa-7db9-42cf-98cc-61438f44a5a6)


### Q2) List the ename,job,sal of the employee who get minimum salary in the company.


### QUERY:
![image](https://github.com/lokeshkrishana/DBMS/assets/119291430/a1561ba1-5103-40bc-9fe4-bae42e6dacf1)

### OUTPUT:
![image](https://github.com/lokeshkrishana/DBMS/assets/119291430/de37c770-1845-487c-b877-8768391d067d)


### Q3) List ename, job of the employees who work in deptno 10 and his/her job is any one of the job in the department ‘SALES’.

### QUERY:
![image](https://github.com/lokeshkrishana/DBMS/assets/119291430/9e6028b0-0cb2-4738-b7e7-6aad5469dcc2)


### OUTPUT:
![image](https://github.com/lokeshkrishana/DBMS/assets/119291430/13c54790-2460-47bb-bc4c-d0aa28a2d9ec)


### Q4) Create a view empv5 (for the table emp) that contains empno, ename, job of the employees who work in dept 10.

### QUERY:
![image](https://github.com/lokeshkrishana/DBMS/assets/119291430/499f79b3-a927-44e7-ba9c-d3328840473c)


### OUTPUT:
![image](https://github.com/lokeshkrishana/DBMS/assets/119291430/e574b981-a826-4169-96f2-85afef3520e6)


### Q5) Create a view with column aliases empv30 that contains empno, ename, sal of the employees who work in dept 30. Also display the contents of the view.

### QUERY:
![image](https://github.com/lokeshkrishana/DBMS/assets/119291430/a457b20c-07e7-4eae-bf22-a3825d6bc28a)


### OUTPUT:
![image](https://github.com/lokeshkrishana/DBMS/assets/119291430/49c85d92-3516-4f74-8438-78f32b4aa572)


### Q6) Update the view empv5 by increasing 10% salary of the employees who work as ‘CLERK’. Also confirm the modifications in emp table

### QUERY:
![image](https://github.com/lokeshkrishana/DBMS/assets/119291430/a6c54a47-3442-4eab-b89d-8db7f0365141)


### OUTPUT:
![image](https://github.com/lokeshkrishana/DBMS/assets/119291430/d81d4548-6b40-49ea-bdfe-e501b025c7b6)


## Create a Customer1 Table
```sql
CREATE TABLE Customer1 (customer_id INT,cust_name VARCHAR(20),city VARCHAR(20),grade INT,salesman_id INT);
```

## Inserting Values to the Table
```sql
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3002, 'Nick Rimando', 'New York', 100, 5001);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3007, 'Brad Davis', 'New York', 200, 5001);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3005, 'Graham Zusi', 'California', 200, 5002);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3008, 'Julian Green', 'London', 300, 5002);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3004, 'Fabian Johnson', 'Paris', 300, 5006);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3009, 'Geoff Cameron', 'Berlin', 100, 5003);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3003, 'Jozy Altidor', 'Moscow', 200, 5007);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3001, 'Brad Guzan', 'London', NULL, 5005);
```

## Create a Salesperson1 table
```sql
CREATE TABLE Salesman1 (salesman_id INT,name VARCHAR(20),city VARCHAR(20),commission DECIMAL(4,2));
```

## Inserting Values to the Table
```sql
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5001, 'James Hoog', 'New York', 0.15);
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5002, 'Nail Knite', 'Paris', 0.13);
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5005, 'Pit Alex', 'London', 0.11);
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5006, 'Mc Lyon', 'Paris', 0.14);
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5007, 'Paul Adam', 'Rome', 0.13);
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5003, 'Lauson Hen', 'San Jose', 0.12);
```

### Q7) Write a SQL query to find the salesperson and customer who reside in the same city. Return Salesman, cust_name and city.

### QUERY:
![image](https://github.com/lokeshkrishana/DBMS/assets/119291430/33eabef8-bb66-4f39-be51-2c82daec23c9)


### OUTPUT:
![image](https://github.com/lokeshkrishana/DBMS/assets/119291430/b441e346-8246-483f-bcfd-1f87ed42c71a)

### Q8) Write a SQL query to find salespeople who received commissions of more than 13 percent from the company. Return Customer Name, customer city, Salesman, commission.


### QUERY:
![image](https://github.com/lokeshkrishana/DBMS/assets/119291430/cbc8608a-57ab-4b32-a523-284839ac2822)


### OUTPUT:
![image](https://github.com/lokeshkrishana/DBMS/assets/119291430/ed1210a8-42b8-4980-b35b-22bdec3bd8b4)

### Q9) Perform Natural join on both tables

### QUERY:

![image](https://github.com/lokeshkrishana/DBMS/assets/119291430/053c96be-5430-4c38-9257-a3449d92cce8)

### OUTPUT:
![image](https://github.com/lokeshkrishana/DBMS/assets/119291430/467edec6-3b75-45e5-9bc0-1a291a3f310a)


### Q10) Perform Left and right join on both tables

### QUERY:
   ## Left Join 
  ![image](https://github.com/lokeshkrishana/DBMS/assets/119291430/6bbf36b6-7645-462a-8851-b87c6b7ba81a)

   ## Right join
  ![image](https://github.com/lokeshkrishana/DBMS/assets/119291430/0831bed2-81f8-4c49-9b17-f3ad6b7d6b2d)

### OUTPUT:
   ## Left Join
  ![image](https://github.com/lokeshkrishana/DBMS/assets/119291430/a94eb39c-dddb-4419-bdb1-d085d414b3c9)


   ## Right Join
  ![image](https://github.com/lokeshkrishana/DBMS/assets/119291430/4232c932-fe0c-4089-b320-c689dd016e76)


## RESULT 
Thus the basics of subqueries,views,joins are performed in SQL.
