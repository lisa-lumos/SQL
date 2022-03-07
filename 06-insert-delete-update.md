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


