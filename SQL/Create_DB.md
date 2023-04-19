Opreating Database
```MYSQL
<!--create databese-->
CREATE DATABASE myDB;

<!--delete-->
DROP DATABASE myDB;

<!--Alter enable reda-only -->
ALTER DATABASE myDB READ ONLY=1;

<!--Alter disable read-only -->
ALTER DATABASE myDB READ ONLY=0;
```
database 'sys' is the system infos of mysql 

Opreating tables
```mysql
CREATE TABLE employees(
	emploee_id INT,
	first_name VARCHAR(50),
	last_name VARCHAR(50),
	hourly_pay DECIMAL(5,2),
	hire_date DATE
);
```

Reaname table:
```mysql
RENAME TABLE workers to employees;
```
Drop table
```mysql
DROP TABLE employees;
```
Add:
```mysql
ADD phone_number VARVHAR(15);
```
change one column
```mysql
<!--change the length-->
ALTER TABLE employees
MODIFY COLUMN email Varchar(100);

<!--change the order -->
ALTER TABLE employees
MODIFY COLUMN email Varchar(100)
AFTER last_time;
```

