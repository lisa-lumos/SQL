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

```sql
select first_name as forename, last_name as surname
from employee;
```

```sql
select distinct gender
from employee;
```

```sql
select count(*)
from employee;
```

Difference between count(*) and count(1)?
- count(*) means it will count all records i.e each and every cell BUT
- count(1) means it will add one pseudo column with value 1 and returns count of all records

```sql
select count(emp_id)
from employee
where gender = 'F';
```

```sql
select avg(salary)
from employee;
```

```sql
select count(gender), gender
from employee
group by gender;
```

`%` means any num of characters, `_` means any one character. 

```sql
select * 
from client 
where client_name like '%LLC';
```

## More complicated queries

```sql
select employee.first_name, employee.last_name
from employee
where employee.emp_id in (
	select works_with.emp_id
	from works_with
	where works_with.total_sales > 30000
);
```














