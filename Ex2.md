# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
## AIM:
To create a manager database and execute DML queries using SQL.


## DML(Data Manipulation Language)
<div align="justify">
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.
</div>

## List of DML commands: 
<div align="justify">
INSERT: It is used to insert data into a table.<br>
UPDATE: It is used to update existing data within a table.<br>
DELETE: It is used to delete records from a database table.<br>
</div>

## Create the table as given below:
```sql
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
```
update managers set salary=salary+(salary*10/100);
```

### OUTPUT:
![dbms2 1](https://github.com/MSowmya28/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/94154791/77f8e92c-434f-4685-879a-ad7880392c0c)


### Q2) Delete the records from manager table where the salary less than 2750.


### QUERY:
```
delete managerss1 where salary<2750;
```


### OUTPUT:
![dbms2 2](https://github.com/MSowmya28/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/94154791/99fc7233-0e02-432a-86e7-31a572804768)


### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)


### QUERY:
```
SELECT
empname AS "empname",
salary*12 AS "Annual Salary"
from
managerss;
```



### OUTPUT:
![dbms2 3](https://github.com/MSowmya28/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/94154791/5848e545-4f68-41b6-8840-7845f2419cc9)


### Q5)	List the names of Clerks from emp table.


### QUERY:
```
select empname from managerss where designation != 'manager';

```

### OUTPUT:
![dbms2 4](https://github.com/MSowmya28/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/94154791/5e868c9c-8c82-4300-8f51-42da5a8cbc8a)




### Q6)	List the names of employee who are not Managers.


### QUERY:
```
select empname from managerss where designation != 'manager';
```


### OUTPUT:
![dbms2 5](https://github.com/MSowmya28/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/94154791/abb2a240-1555-4ff3-a11b-f973f42c4b8a)


### Q7)	List the names of employees not eligible for commission.


### QUERY:
```
select empname from managerss where commission = 0;
```


### OUTPUT:
![dbms2 6](https://github.com/MSowmya28/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/94154791/59ec9d60-9aeb-47ed-8310-6774ddca72eb)



### Q8)	List employees whose name either start or end with ‘s’.


### QUERY:
```
select empname from managerss where empname LIKE 's%' OR empname LIKE '%s';
```

### OUTPUT:
![dbms2 7](https://github.com/MSowmya28/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/94154791/de5e736a-3a47-43c4-ba7c-23ca92b92a5b)



### Q9) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.


### QUERY:
```
select empname,designation,deptno,hiredate from managerss order by hiredate ASC;
```

### OUTPUT:
![dbms2 8](https://github.com/MSowmya28/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/94154791/98183c8e-7384-4d02-9536-7275b0f20c52)


### Q10) List the Details of Employees who have joined before 30 Sept 81.


### QUERY:
```
select * from managerss where hiredate < '30 SEP 81';
```



### OUTPUT:
![dbms2 9](https://github.com/MSowmya28/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/94154791/84a98f39-bdaf-4b8d-8c07-8696288461fe)



### Q11)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.


### QUERY:
```
select empname,deptno,salary from managerss ORDER BY deptno ASC,salary desc;
```


### OUTPUT:
![dbms2 10](https://github.com/MSowmya28/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/94154791/e17efdb5-f3c4-448e-a145-85e348dc10e9)



### Q12) List the names of employees not belonging to dept no 30,40 & 10


### QUERY:
```
select empname from managerss where deptno NOT IN (30,40,10);
```


### OUTPUT:
![dbms2 11](https://github.com/MSowmya28/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/94154791/aafdf779-0eb1-4799-9cb7-715afd12662e)


### Q13) Find number of rows in the table EMP

### QUERY:
```
select count(*) as rownumber from managerss;
```


### OUTPUT:
![dbms2 12](https://github.com/MSowmya28/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/94154791/86372300-a257-4741-a8e0-c6f526ce2f79)



### Q14) Find maximum, minimum and average salary in EMP table.

### QUERY:
```
select MAX(salary) as maximumsal,MIN(salary) as minimusal,AVG(salary) as averagesal from managerss;
```
### OUTPUT:
![dbms2 13](https://github.com/MSowmya28/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/94154791/3dadb012-3e0e-42b2-9166-da48af453e5a)


### Q15) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```
select designation,count(*) as number_employee from managerss GROUP BY
DESIGNATION ORDER BY number_employee DESC;
```



### OUTPUT:
![dbms2 14](https://github.com/MSowmya28/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/94154791/52e71a5c-0876-4460-98d8-b7aea95e60d7)


## RESULT:
Executing DML queries using SQL was executed successfully.
