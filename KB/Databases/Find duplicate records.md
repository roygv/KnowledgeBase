## Table my_duplicates
| key | value |
| --- | ----- |
| 1   | Joe   |
| 2   | Jane  |
| 3   | Jim   |
| 3   | Jim   |
| 4   | Joe   |
| 4   | Joe   |
| 4   | Joe   |

## Solution
```sql
with t as ( -- Prepare table
select 1 as key, 'Joe' as value union all
select 2, 'Jane' union all
select 3, 'Jim' union all
select 3, 'Jim'union all
select 4, 'Joe' union all
select 4, 'Joe' union all
select 4, 'Joe'
)
-- Query
select key,value, count(*) num_duplicates 
  from t 
 group by key, value 
having count(*) > 1
```