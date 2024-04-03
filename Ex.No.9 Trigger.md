# Ex. No: 6 PL/SQL program using Triggers 
### DATE: 
### AIM: To create PL/SQL program to display new and old salary of customer when before/ after updation takes place. 

### Steps:
1. Create a trigger for each row when updation occurs.
2. Declare the variable in Declare section.
3. Start the begin section.
4. Calculate the salary changes.
5. Display the result 
6. End the begin section.

### Program:

CREATE TABLE employed(
  empid NUMBER,
  empname VARCHAR2(10),
  dept VARCHAR2(10),
  salary NUMBER
);

CREATE TABLE sal_log (
  log_id NUMBER GENERATED ALWAYS AS IDENTITY,
  empid NUMBER,
  empname VARCHAR2(10),
  old_salary NUMBER,
  new_salary NUMBER,
  update_date DATE
);
### Output:

Create employee table

![image](https://github.com/lokeshkrishana/DBMS/assets/119291430/fc21e423-99ba-46d6-ab17-3071bd539dce)

Create salary_log table

![image](https://github.com/lokeshkrishana/DBMS/assets/119291430/c24cd2fe-741c-44f8-8665-496dec39c46a)

PLSQL Trigger code

-- Create the trigger
CREATE OR REPLACE TRIGGER log_sal_update
BEFORE UPDATE ON employed
FOR EACH ROW
BEGIN
  IF :OLD.salary != :NEW.salary THEN
    INSERT INTO sal_log (empid, empname, old_salary, new_salary, update_date)
    VALUES (:OLD.empid, :OLD.empname, :OLD.salary, :NEW.salary, SYSDATE);
  END IF;
END;
/
-- Insert the values in the employee table
insert into employed values(1,'GOJO','HR',100000);
insert into employed values(2,'Yuta','SALES',500000)


-- Update the salary of an employee
UPDATE employed
SET salary = 60000
WHERE empid = 1;
-- Display the employee table
SELECT * FROM employed;

-- Display the salary_log table
SELECT * FROM sal_log;

Output:

![image](https://github.com/lokeshkrishana/DBMS/assets/119291430/f14174db-7433-4c00-9f37-ff1820d21f11)

### Result:
Thust the program was performed sucessfully.
