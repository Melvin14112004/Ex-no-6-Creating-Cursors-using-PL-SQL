# Ex. No: 6 Creating Cursors using PL/SQL

## DATE:8.9.23

### AIM: To create a cursor using PL/SQL.

### Steps:
1. Create employee table with following attributes (empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
2. Create a cursor named as employee_cursor
3. Using cursor read each record and display the result
4. Close the cursor

### Program:
```
CREATE TABLE employd (empid NUMBER,empname VARCHAR(10),dept VARCHAR(10),salary NUMBER);
INSERT INTO employd VALUES (01, 'Clara', 'PR', 220000);
INSERT INTO employd VALUES (02, 'Suheela', 'Marketing', 110000);

```

### PLSQL Cursor code
```
SET SERVEROUTPUT ON;
DECLARE
   CURSOR employd_cursor IS
   SELECT empid,empname,dept,salary
   FROM employd;
   emp_id NUMBER;
   emp_name VARCHAR(50);
   emp_dept VARCHAR(50);
   emp_salary NUMBER;
BEGIN
  OPEN employd_cursor;

  LOOP
    FETCH employd_cursor INTO emp_id, emp_name, emp_dept, emp_salary;

    EXIT WHEN employd_cursor%NOTFOUND;

    DBMS_OUTPUT.PUT_LINE('Employee ID: ' || emp_id);
    DBMS_OUTPUT.PUT_LINE('Employee Name: ' || emp_name);
    DBMS_OUTPUT.PUT_LINE('Department: ' || emp_dept);
    DBMS_OUTPUT.PUT_LINE('Salary: ' || emp_salary);
  END LOOP;

  CLOSE employd_cursor;
END;
```
### Output:
![Screenshot 2023-10-08 151843](https://github.com/Melvin14112004/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/129204995/e691fdd4-76e0-4a11-8709-f02dbb86c5bb)

### Result:
The Program has been implemented successfully.
