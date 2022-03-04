## Join tables (add more fields)

MySQL `join` means same with `inner join`. 

```sql
select employee.emp_id, employee.first_name, branch.branch_name
from 
	employee 
	join 
	branch
	on employee.emp_id = branch.mgr_id;
```

```sql
select employee.emp_id, employee.first_name, branch.branch_name
from 
	employee 
	left join 
	branch
	on employee.emp_id = branch.mgr_id;
```

```sql
select employee.emp_id, employee.first_name, branch.branch_name
from 
	employee 
	right join 
	branch
	on employee.emp_id = branch.mgr_id;
```

MySQL doesn't have cross join. 




































