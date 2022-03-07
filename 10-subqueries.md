Return the employees whose salary is greater than average:

```sql
select emp_name, salary 
from employees where salary > (select avg(salary) from employees);
```

Return the employees whose salary is greater than John's salary: 

```sql
select emp_name 
from employees
where salary > (select salary from employees where emp_name = 'John');
```

Across two tables:

```sql
select product_id, product_name from products
where product_id in (select product_id from order_details where unit_price < 100);
```
























