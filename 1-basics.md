# SQL Notes - Basics

## Basic concepts

DBMS: Database Management System

C.R.U.D stands for Create, Read, Update and Delete. 

Two types of databases: 
1. Relational Databases (SQL)
2. Non-Relational (noSQL)

SQL: structured query language for interacting with Relational DBMS. 

SQL is basically 4 types of languages in one: 
- DQL: Data Query Language
- DDL: Data Definition Lanugage
  - Used for defining database schemas
- DCL: Data Control Language
  - Used to control access to data in the database
- DML: Data Manipulation Language
  - Used to insert, delete or update data in the database

Query: requests made to the DBMS for specific information. 

Primary key: A special relational database table column (or combination of columns) designated to uniquely identify each table record. 

Foreign key: A column or group of columns in a relational database table that provides a link between data in two tables. A table can have multiple foreign keys that refer to different tables respectively. 

Composite key: A candidate key that consists of two or more columns that together uniquely identify a row.

## Common datatypes in MySQL

| Datatype | Description |
| ---------------- | ----------- |
| VARCHAR(size) | The size parameter specifies the maximum length in characters - 0 to 65535 |
| INT(size) | The size parameter specifies the maximum display width |
| DECIMAL(size, d) | The total number of digits is specified in size. The number of digits after the decimal point is specified in d. Default: size = 10, d = 0 |
| BLOB(size) | Binary Large Objects |
| DATE | Format: YYYY-MM-DD |
| TIMESTAMP | Format: YYYY-MM-DD hh:mm:ss |

## Creating tables

```sql
create table student (
	student_id int primary key,
	name varchar(20) not null,
	major varchar(20) unique
);
```

or 

```sql
create table student (
	student_id int,
	name varchar(20),
	major varchar(20) default 'undecided',
	primary key (student_id)
);
```

Below branch table has foreign key mgr_id, and if a row is deleted from employee table, then in branch table, the corresponding mgr_id will be set to null. 

```sql
create table branch (
	branch_id int primary key,
	branch_name varchar(40),
	mgr_id int,
	mgr_start_date date,
	foreign key (mgr_id) references employee(emp_id) on delete set null
);
```

Similarly, below `cascade` will delete the corresponding mgr_id from branch table:

```sql
create table branch (
	branch_id int primary key,
	branch_name varchar(40),
	mgr_id int,
	mgr_start_date date,
	foreign key (mgr_id) references employee(emp_id) on delete cascade
);
```


## Show table information

```sql
describe student;
```

## Drop table

```sql
drop table student;
```

## Add a column to table

```sql
alter table student add gpa decimal(3, 2);
```

## Drop a column of table

```sql
alter table student drop column gpa;
```

## Modify definition of table 

```sql
alter table branch 
add foreign key (mgr_id)
references employee(emp_id)
on delete set null;
```


## Show table contents

```sql
select * from student;
```

```sql
select name, major 
from student;
```

```sql
select student.name, student.major
from student
order by name desc, student_id
limit 2;
```

```sql
select * 
from student
where name in ('Clare', 'Kate', 'Mike');
```



## Insert  into table

```sql
insert into student values (1, 'Jack', 'Biology');
```

```sql
insert into student (student_id, name) values (2, 'Kate');
```

## Update table

```sql
update student
set major = 'Bio'
where major = 'Biology';
```

```sql
update student
set major = 'Bio'
where student_id = 4 or major = 'Biology';
```

## Delete from table

```sql
delete from student
where student_id = 5;
```

```sql
```

















































