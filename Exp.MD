# SQL ASSIGNMENTS

---

# Assignment 1

### Objective:
Perform table creation and modification queries using the Employee table.

---

### 1. Create Employee_Master table with data using Employee table.

~~~sql
CREATE TABLE Employee_Master AS
SELECT * FROM Employee;
~~~

---

### 2. Delete all records in Employee_Master where DeptNo is 10.

~~~sql
DELETE FROM Employee_Master
WHERE DeptNo = 10;
~~~

---

### 3. Update 10% increase in salary of employees in DeptNo = 20 in Employee_Master.

~~~sql
UPDATE Employee_Master
SET Sal = Sal + (Sal * 0.10)
WHERE DeptNo = 20;
~~~

---

### 4. Alter column SAL to size NUMBER(10,2) in Employee_Master.

~~~sql
ALTER TABLE Employee_Master
MODIFY Sal NUMBER(10,2);
~~~

---

### 5. Drop Employee_Master table.

~~~sql
DROP TABLE Employee_Master;
~~~

---

<br>

# Assignment 2



### Objective:
Write SQL queries using sorting, pattern matching, filtering and calculations.

---

### 1. List all employees and jobs in Department 30 in descending order by salary.

~~~sql
SELECT Ename, Job
FROM Employee
WHERE DeptNo = 30
ORDER BY Sal DESC;
~~~

---

### 2. List job and Department Number of employees whose name begins with "A" and ends with "N".

~~~sql
SELECT Job, DeptNo
FROM Employee
WHERE Ename LIKE 'A%N';
~~~

---

### 3. Display the name of employees whose name starts with alphabet S.

~~~sql
SELECT Ename
FROM Employee
WHERE Ename LIKE 'S%';
~~~

---

### 4. Display the names of employees whose name ends with alphabet S.

~~~sql
SELECT Ename
FROM Employee
WHERE Ename LIKE '%S';
~~~

---

### 5. Display the names of employees working in department 10, 20 or 40 or employees working as clerk, salesman or analyst.

~~~sql
SELECT Ename
FROM Employee
WHERE DeptNo IN (10, 20, 40)
   OR Job IN ('CLERK', 'SALESMAN', 'ANALYST');
~~~

---

### 6. Display employee number and names for employees who earn commission.

~~~sql
SELECT EmpNo, Ename
FROM Employee
WHERE Comm IS NOT NULL;
~~~

---

### 7. Display employee number and total salary for each employee.

~~~sql
SELECT EmpNo, (Sal + NVL(Comm,0)) AS Total_Salary
FROM Employee;
~~~

---

### 8. Display employee number and annual salary for each employee.

~~~sql
SELECT EmpNo, (Sal * 12) AS Annual_Salary
FROM Employee;
~~~

---

### 9. Display the names of all employees working as clerks and drawing a salary more than 3000.

~~~sql
SELECT Ename
FROM Employee
WHERE Job = 'CLERK'
AND Sal > 3000;
~~~

---

### 10. Display the names of employees who are working as clerk, salesman or analyst and drawing a salary more than 3000.

~~~sql
SELECT Ename
FROM Employee
WHERE Job IN ('CLERK', 'SALESMAN', 'ANALYST')
AND Sal > 3000;
~~~

---

<br>

# Performing Queries using Employee Table (Retrieving Data)


### Objective:
Retrieve specific data using SELECT statements.

---

### 1. List all distinct jobs in Employee.

~~~sql
SELECT DISTINCT Job
FROM Employee;
~~~

---

### 2. List all information about employees in Department Number 30.

~~~sql
SELECT *
FROM Employee
WHERE DeptNo = 30;
~~~

---

### 3. Find all department numbers with department numbers greater than 20.

~~~sql
SELECT DeptNo
FROM Department
WHERE DeptNo > 20;
~~~

---

### 4. Find all information about all the managers as well as the clerks in department 30.

~~~sql
SELECT *
FROM Employee
WHERE (Job = 'MANAGER' OR Job = 'CLERK')
AND DeptNo = 30;
~~~

---

### 5. List the Employee name, Employee numbers and department of all clerks.

~~~sql
SELECT Ename, EmpNo, DeptNo
FROM Employee
WHERE Job = 'CLERK';
~~~

---

### 6. Find all managers not in department 30.

~~~sql
SELECT *
FROM Employee
WHERE Job = 'MANAGER'
AND DeptNo <> 30;
~~~

---

### 7. List information about all employees in department 10 who are not managers or clerks.

~~~sql
SELECT *
FROM Employee
WHERE DeptNo = 10
AND Job NOT IN ('MANAGER', 'CLERK');
~~~

---

### 8. Find employees and jobs earning between 1200 and 1400.

~~~sql
SELECT Ename, Job
FROM Employee
WHERE Sal BETWEEN 1200 AND 1400;
~~~

---

### 9. List Name and Department Number of employees who are clerk, analyst or salesman.

~~~sql
SELECT Ename, DeptNo
FROM Employee
WHERE Job IN ('CLERK', 'ANALYST', 'SALESMAN');
~~~

---

### 10. List Name and Department Number of employees whose name began with M.

~~~sql
SELECT Ename, DeptNo
FROM Employee
WHERE Ename LIKE 'M%';
~~~

---

