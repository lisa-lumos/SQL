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


