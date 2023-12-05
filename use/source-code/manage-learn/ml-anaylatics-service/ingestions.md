# Ingestions

There are two types of ingestion

## Batch Ingestion

Batch ingestion refers to a data processing technique where data is collected and processed in discrete, predefined groups or batches rather than processed in real-time or as a continuous stream.

<figure><img src="../../../../.gitbook/assets/ml-analytics (1).jpg" alt=""><figcaption></figcaption></figure>

Pyspark scripts are scheduled to ingest the data batch-wise to druid data sources.

Batch Scripts in ML Analytics

In Manage Learn batch ingestion, we have 2 types of ingestions.

1. Delete and Re ingest: Since Druid does not support update operation, we have come up with an approach to delete the entire data source and re-ingest the complete data from Mongo so that it will have the updated data. The data in this data source is used for program dashboard CSV reports.
2. Append: Apart from the delete and ingest we also have aggregated data sources that appends the new data. In this approach, the entire Mongo is queried and the newly aggregated data is appended to the data source.

Note: In the above-discussed approaches, we have applied a duplication logic to scripts of aggregated data sources. So in case of any failure in scheduled jobs, we will have to run the jobs manually. In such cases, deleting and re-ingest kind of data sources will not have data discrepancies due to duplicate runs because it is deleting the data and ingesting all the data, however, the append kind of ingestion might have data discrepancies if it is a duplicate run. Hence we have used Mongo to log the details and avoid such scenarios.

\\

### Project ( Daily )

1. py\_gather\_program.py - This script gathers all program\_id's from MongoDB and stores it into a text file.
2. pyspark\_project\_deletion\_batch.py - This script deletes all segments in the Druid project data source.
3. pyspark\_project\_batch.py - This script takes program ID as input, fetches the data from MongoDB, flattens the data, and puts it into Druid.
4. pyspark\_prj\_status.py - This script creates an aggregated data source.
5. pyspark\_prj\_status\_prglevel.py - This script creates an aggregated data source at the program level, providing a high-level view with all status information.\\

### Observation ( Daily )

1. pyspark\_observation\_status\_batch.py - This script fetches the data related to Observation submissions with all statuses from MongoDB, flattens the data, and puts it into Druid.
2. pyspark\_obs\_status\_batch.py - This script creates an aggregated data source for observation status level information.
3. pyspark\_obs\_domain\_criteria\_batch.py - This script creates an aggregated data source for observation to domain\_criteria level information.
4. pyspark\_obs\_domain\_batch.py - This script creates an aggregated data source for observation to domain level information.\\

### Survey ( Daily )

1. pyspark\_survey\_status.py - This script fetches the data related to survey submission information with status from MongoDB, flattens the data, and puts it into Druid.
2. pyspark\_sur\_status.py - This script creates an aggregated data source for survey status-level information.

These jobs will run at daily midnight

### To run Batch Scripts in ML Analytics, follow these steps:

1. Log in to the ML Analytics server using your credentials.
2. After logging in, switch to the data-pipeline user account using the following command.

`sudo su data-pipeline`

3. Once you are logged in as the data-pipeline user, navigate to the directory where the batch scripts are located. In this case, the directory is /opt/sparkjobs/ml-analytics-service/. Use the cd command to change to that directory.

```
cd /opt/sparkjobs/ml-analytics-service/
```

4. Now, execute the run.sh script to run all the batch scripts:

./run.sh

The run.sh script likely contains commands to execute the individual batch scripts one by one, or it may execute a specific batch processing workflow. Running this script will trigger the execution of all the specified batch scripts, and they will perform their respective tasks as described in the documentation.

## Real-time Ingestion

Real-time ingestion with Kafka refers to the process of continuously collecting and processing data in real time using Apache Kafka.

<figure><img src="../../../../.gitbook/assets/RealTime_ml_analytics (1) (1).jpg" alt=""><figcaption></figcaption></figure>

Real-time scripts in ML Analytics

### Observation

1. py\_observation\_streaming.py - This script serves as a Kafka stream processor. It consumes data from a specified Kafka topic containing observations. The script processes the incoming observations, which likely include question-level information, and then publishes the processed data to another Kafka topic.
2. py\_observation\_evidence\_streaming.py - This script serves as a Kafka stream processor. It consumes data from a specified Kafka topic containing observations. The script processes the incoming observations, extracting evidence-level information, and then publishes the processed data to another Kafka topic dedicated to evidence-level information.

### Survey

1. py\_survey\_streaming.py - This script serves as a Kafka stream processor. It consumes data from a specified Kafka topic containing a survey. The script processes the incoming survey, and then publishes the processed data to another Kafka topic.
2. py\_survey\_evidence\_streaming.py - This script serves as a Kafka stream processor. It consumes data from a specified Kafka topic containing survey. The script processes the incoming survey, extracting evidence-level information, and then publishes the processed data to another Kafka topic dedicated to evidence-level information.

### To run real-time scripts.

Open a terminal or SSH into the server where the real-time scripts need to be executed.

Start a new Tmux session `tmux new -s my_session` and open that session run this CMD

`python {{ script_name}}.py worker -l info`

Save and close the session.

\
\\
