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

