## Installation
https://community.getdbt.com/
```bash
pip install dbt-snowflake
# To create a new project
dbt init <project-name>
cd <project-name>
# To test configuration and connection
dbt debug
```

## Documentation
https://docs.getdbt.com/docs/configure-your-profile
## Tips
https://github.com/erika-e/dbt-tips
```
dbt debug --config-dir   # where is my config
dbt debug --profile <name>  # set currentt profile (Overrides dbt_project.yml)
```
## Cheatsheet
https://datacaffee.com/wp-content/uploads/2021/03/dbt-_commands.pdf
## Terminology
- [Source](https://docs.getdbt.com/docs/build/sources): Externally updated tables that a source for transformations (usually by ELT)
- [Seed](https://docs.getdbt.com/docs/build/seeds): CSV files in your dbt project (typically in your `seeds` directory), that dbt can load into your DWH
- [Snapshot](https://docs.getdbt.com/docs/build/snapshots): creates a SCD2 table from a regular mutable table
- [Model](https://docs.getdbt.com/docs/build/models): 
- [Exposure](https://docs.getdbt.com/docs/build/exposures): Exposures make it possible to define and describe a downstream use of your dbt project, such as in a dashboard, application, or data science pipeline
- [Metric](https://docs.getdbt.com/docs/build/metrics): A metric is an aggregation over a table that supports zero or more dimensions
- 