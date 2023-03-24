Data Pipelines with Airflow



## Introduction
A music streaming company, Sparkify, has decided that it is time to introduce more automation and monitoring to their data warehouse ETL pipelines and come to the conclusion that the best tool to achieve this is Apache Airflow.

They have decided to bring you into the project and expect you to create high grade data pipelines that are dynamic and built from reusable tasks, can be monitored, and allow easy backfills. They have also noted that the data quality plays a big part when analyses are executed on top the data warehouse and want to run tests against their datasets after the ETL steps have been executed to catch any discrepancies in the datasets.

The source data resides in S3 and needs to be processed in Sparkify's data warehouse in Amazon Redshift. The source datasets consist of JSON logs that tell about user activity in the application and JSON metadata about the songs the users listen to.



## Project Tool
Python, Airflow, RedShift



## Data Sources
For this project, you'll be working with two datasets. Here are the s3 links for each:
Log data: s3://udacity-dend/log_data
Song data: s3://udacity-dend/song_data



## Prerequisites:
Create an IAM User in AWS.
Follow the steps on the page Create an IAM User in AWS in the lesson Data Pipelines.

Create a redshift cluster in AWS.
Follow the steps on the page Create an AWS Redshift Cluster in the lesson Data Pipelines. Ensure that you are creating this cluster in the us-west-2 region. This is important as the s3-bucket that we are going to use for this project is in us-west-2.



## Data Structure
star schema is used to for this data ETL, there are one fact table and 4 dimension tables

Fact Table: songplays
Dimension Tables； users， songs， artists， time



## Project Workspace Structure

udac_example_dag.py - The DAG set up code which runs in airflow it is under airflow/dags

there are four operators under airflow/plugins/operators
stage_redshift.py - copy data from S3 to redshift stage tables
load_fact.py - insert data into the fact table
load_dimension.py - insert data into the dimension tables
data_quality.py - table data quality check



## Airflow run snapshot
there is a snapshot to show the airflow run, it is under image/