## Summary

A music streaming startup, Sparkify, has grown their user base and song database and want to move their processes and data onto the cloud. Their data resides in S3, in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

Hence in order to ease things for them, a Data Warehouse with AWS RedShift is implemented along with an ETL pipeline that extracts data from S3, stages them in Redshift, and transforms data into a set of Fact and Dimensional tables for their analytics team.

This solution enables Sparkify to easily process large amounts of information efficiently.

## Database schema

| Table Type | Table Name | Description |
| ---- | ---- | ---- |
| Staging Table | staging_events | staging table for event data |
| Staging Table | staging_songs | staging table for song data |
| Fact Table | songplays | information how songs were played, e.g. when by which user in which session | 
| Dimension Table | users | user-related information such as name, gender and level | 
| Dimension Table | songs | song-related information containing name, artist, year and duration | 
| Dimension Table | artists | artist name and location | 
| Dimension Table | time | time-related information for timestamps |

## ETL pipeline

1. Load song and log data both from S3 buckets.
2. Stage the loaded data.
3. Transform the data into the above described data schema.

## Project instructions

1. Setup a redshift cluster on AWS and insert the connection details in `dwh.cfg`.
2. Create the needed the database structure by executing `create_tables.py`.
3. Process the data from the configured S3 data sources by executing `etl.py`.

 

