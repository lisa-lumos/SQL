A code you can save and reuse again and again. 

```sql
delimiter &&
create procedure top_player()
begin
select name, country, goals
from players where goals > 6;
end &&
delimiter ;

call top_player();
```

Stored procedure using IN parameter: 

```sql
delimiter //
create procedure sp_sortBySalary(IN var int)
begin
select name, age, salary 
from emp_details
order by salary desc
limit var;
end //
delimiter ;

call sp_sortBySalary(3);
```


```sql
delimiter //
create procedure update_salary(in tmp_name varchar(20), in new_salary float)
begin
update emp_details
set salary = new_salary
where emp_name = tmp_name;
end //
delimiter ;

call update_salary('Marry', 80000);
```

SP using OUT parameter:

```sql
delimiter //
create procedure count_emp(out total_emp int)
begin
select count(name) into total_emp 
from emp_details
where gender = 'F';
end //
delimiter ;

call count_emp(@F_emp);
select @F_emp as female_emps; 
```











