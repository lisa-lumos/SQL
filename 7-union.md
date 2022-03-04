## Stack results together (add rows)

```sql
select first_name
from employee
union
select branch_name
from branch;
```

```sql
select first_name
from employee
union
select branch_name
from branch
union
select client_name
from client;
```

```sql
select first_name as names
from employee
union
select branch_name
from branch
union
select client_name
from client;
```

```sql
select client_name, id
from client
union
select branch_name, id
from branch;
```

```sql
select client.client_name, client.id
from client
union
select branch.branch_name, branch.id
from branch;
```

















