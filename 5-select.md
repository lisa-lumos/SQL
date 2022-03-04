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

`/%` means any num of characters, `/_` means any one character. 

```sql
select * 
from client 
where client_name like '%LLC';
```

