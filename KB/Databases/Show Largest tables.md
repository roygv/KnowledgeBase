## Top schemas by space used (Big Query)
```sql
select table_schema,
		round(sum(total_physical_bytes)/POW(1024,3),0) AS physical_GB,
		round(sum(TOTAL_LOGICAL_BYTES)/POW(1024,3),0) AS logical_GB,
		count(*) num_tables
from `region-us`.INFORMATION_SCHEMA.TABLE_STORAGE
-- Can limit to `<project-id>`.`region-us`.INFORMATION_SCHEMA...
group by 1
order by 2 desc
```
## Top tables by space used (Big Query)
```sql
select  table_name,
		round(sum(total_physical_bytes)/POW(1024,3),0) AS physical_GB,
		round(sum(TOTAL_LOGICAL_BYTES)/POW(1024,3),0) AS logical_GB,
		sum(total_rows)
from `region-us`.INFORMATION_SCHEMA.TABLE_STORAGE
group by 1
order by 2 desc
limit 10
```
## Top tables by number of rows (Big Query)
```sql
select  table_name,
		round(sum(total_physical_bytes)/POW(1024,3),0) AS physical_GB,
		round(sum(TOTAL_LOGICAL_BYTES)/POW(1024,3),0) AS logical_GB,
		sum(total_rows) as total_rows
from `region-us`.INFORMATION_SCHEMA.TABLE_STORAGE
group by 1
order by 4 desc
limit 10
```

