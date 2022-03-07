```sql
delimiter //
create trigger marks_verify
before insert
on student
for each row
if new.mark < 0 then set mark = 50;
end if; //

insert into student values
(1, 75.0),
(2, -20.0),
(3, 90.5),
(4, -12.5);

drop trigger marks_verify;
```