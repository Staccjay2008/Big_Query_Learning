##### Revert the table to old versions based on the timestamp.
###### BigQuery lets you use time travel to access data stored in BigQuery that has been changed or deleted. You can access the data from any point within the last seven days

```SQL
SELECT * FROM `project_id.database_id.table_id` FOR SYSTEM_TIME AS OF TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 200 minute)
```

##### create stored procedures

```SQL
CREATE OR REPLACE PROCEDURE `project_id.database_id.table_id`()
BEGIN
-- declare variable_name data_type;
-- set variable_name = (select ...);
--if variable_name < 5 then
--create; insert; update; delete;
--end if;

END;
```
#### archive tables

```SQL
CREATE OR REPLACE PROCEDURE `project_id.database_id.table_id`()
BEGIN

declare curr_date string; -- declare variable_name data_type;
set curr_date = format_date ('%E4Y%m%d', current_date ());  -- set variable_name = (select ...);

execute immediate
concat("create or replace table `project_id.database_id.table_id_",curr_date,"`"," as select * from `project_id.database_id.table_id`");
END;
```
