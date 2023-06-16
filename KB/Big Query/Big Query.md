![|70](bigquery.png)
BigQuery is a completely serverless and cost-effective enterprise data warehouse. It has built-in machine learning and BI that works across clouds, and scales with your data.
## Cost tips
### Using physical vs. logical storage pricing
Each dataset can be set to be billed based on logical space required or physical (compressed) space. The later costs about double but compression ratios are often higher that x2.
An [article](https://cloud.google.com/bigquery/docs/information-schema-table-storage) that explains it (and required permissions)
A query to compare the cost of both options:
```sql
DECLARE active_logical_gb_price FLOAT64 DEFAULT 0.02;
DECLARE long_term_logical_gb_price FLOAT64 DEFAULT 0.01;
DECLARE active_physical_gb_price FLOAT64 DEFAULT 0.04;
DECLARE long_term_physical_gb_price FLOAT64 DEFAULT 0.02;

WITH
storage_sizes AS (
SELECT
	table_schema AS dataset_name,
	SUM(active_logical_bytes) / power(1024, 3) AS active_logical_gb,
	SUM(long_term_logical_bytes) / power(1024, 3) AS long_term_logical_gb,
	SUM(active_physical_bytes) / power(1024, 3) AS active_physical_gb,
	SUM(long_term_physical_bytes) / power(1024, 3) AS long_term_physical_gb,
	SUM(total_physical_bytes) / power(1024, 3) AS total_physical_gb,
	SUM(total_logical_bytes) / power(1024, 3) AS total_logical_gb
FROM region-us.INFORMATION_SCHEMA.TABLE_STORAGE_BY_PROJECT
WHERE total_logical_bytes > 0
AND total_physical_bytes > 0
GROUP BY 1
)
SELECT
	dataset_name,
	active_logical_gb,
	long_term_logical_gb,
	active_physical_gb,
	long_term_physical_gb,
	total_logical_gb / total_physical_gb AS compression_ratio,
	active_logical_gb * active_logical_gb_price AS active_logical_cost,
	long_term_logical_gb * long_term_logical_gb_price AS long_term_logical_cost,
	active_physical_gb * active_physical_gb_price AS active_physical_cost,
	long_term_physical_gb * long_term_physical_gb_price AS long_term_physical_cost,
	((active_logical_gb * active_logical_gb_price) + (long_term_logical_gb * long_term_logical_gb_price))
	- ((active_physical_gb * active_physical_gb_price) + (long_term_physical_gb * long_term_physical_gb_price)) AS total_cost_difference
FROM storage_sizes
ORDER BY compression_ratio DESC;
```
Command to switch to physical billing mode:
```sql
ALTER SCHEMA <dataset-name>
SET OPTIONS(storage_billing_model = 'physical');
```

To connect to the database using postgres wire protocol:
`psql -h localhost -U root Imported`
password: playwithdata

To open the GUI:
`http://localhost:2480/`
user: root
password: playwithdata

