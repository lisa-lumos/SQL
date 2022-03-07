Window functions add new field(s) to each row in the table, similar to "creating a calculated field" in Tableau. It is interesting to compare it with aggregation. 

```sql
select emp_name, age, dept, 
sum(salary) over (partition by dept) as total_salary
from employees;
```

```sql
select row_number() over (order by salary) as row_num, 
emp_name, salary 
from employees
order by salary;
```

If there were duplicated records in the student table, below script will show row_num starting from 1, incremental, for each partition. 

```sql
select student_id, student_name, 
row_number() over (partition by student_id, student_name order by student_id) as row_num
from student;
```

```sql
select num_of_orders, rank() over (order by num_of_orders) as rank
from customers;
```

```sql
select emp_name, age, salary, 
first_value(emp_name) over (partition by dept order by salary desc) as highest_salary_in_dept 
from employees;
```







