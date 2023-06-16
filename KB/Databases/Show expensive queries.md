## Longest running queries
```sql
select user_email, 
	   statement_type, 
	   query, 
	   timeline[offset(0)].elapsed_ms, 
	   total_bytes_billed
from `edw-prod-153420`.`region-us`.INFORMATION_SCHEMA.JOBS_BY_USER
order by 4 desc
limit 10
```
## Most expensive queries
```sql
select user_email, 
	   statement_type, 
	   query, 
	   timeline[offset(0)].elapsed_ms, 
	   total_bytes_billed
from `edw-prod-153420`.`region-us`.INFORMATION_SCHEMA.JOBS_BY_USER
order by 5 desc
```