```sql
create view cust_details
as
select custumerName, phone, city
from 
customers;
```

Create a view by joining two tables:

```sql
create view product_description
as
select product_name, quantity, msrp, textdescription 
from products as p
join
productlines as pl
on p.productline = pl.productline;

select * from product_description;
```

To rename a veiw: 

```sql
rename table product_description
to vehicle_description;
```

Display veiws:

```sql
show full tables
where table_type = 'VIEW';
```

Drop a view:

```sql
drop view vehicle_description;
```





