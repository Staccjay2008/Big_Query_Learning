##### Revert the table to old versions based on the timestamp.
###### BigQuery lets you use time travel to access data stored in BigQuery that has been changed or deleted. You can access the data from any point within the last seven days

```SQL
SELECT * FROM `project_id.database_id.table_id` FOR SYSTEM_TIME AS OF TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 200 minute)
```

##### create stored procedures

```SQL
CREATE OR REPLACE PROCEDURE `project_id.database_id.table_id`()
BEGIN

create; insert; update;delete;

END;
```
