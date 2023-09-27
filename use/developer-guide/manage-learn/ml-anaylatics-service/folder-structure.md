# Folder Structure

.

├── LICENSE

├── README.md&#x20;

├── back-up\_reports\_configs

│   ├── pre\_prod\_reports

│   └── prod\_reports

├── cloud\_storage

│   ├── \_\_init\_\_.py

│   ├── aws.py

│   ├── cloud.py

│   ├── gcp.py

│   ├── ms\_azure.py

│   ├── oracle.py

│   └── py\_cloud\_migration.py

├── config.ini&#x20;

├── config.sample

├── druid\_data\_product\_query\_config.txt

├── hp\_reports\_metrics

│   └── hawkeye\_report\_metric.py

├── manual\_report\_scripts

│   ├── domain\_criteria\_report.py

│   ├── question\_domain\_criteria\_report.py

│   ├── question\_report.py

│   └── status\_report.py

├── migrations

│   ├── lib

│   └── releases

├── observations

│   ├── ml\_observation\_faust-data

│   ├── py\_observation\_batch\_del\_update.py

│   ├── py\_observation\_evidence\_streaming.py

│   ├── py\_observation\_evidence\_streaming\_batch\_refreshment.py

│   ├── py\_observation\_streaming.py

│   ├── py\_observation\_streaming\_update\_druid\_data.py

│   ├── pyspark\_obs\_domain\_batch.py

│   ├── pyspark\_obs\_status\_batch.py

│   ├── pyspark\_observation\_rollup.py

│   ├── pyspark\_observation\_status\_batch.py

│   ├── pyspark\_observation\_streaming\_refreshment\_batch.py

│   ├── pyspark\_temp\_punjab\_entities.py

│   └── pyspark\_temp\_script\_add\_cols.py

├── projects

│   ├── \_\_pycache\_\_

│   ├── py\_gather\_program.py

│   ├── pyspark\_project\_batch \_entire\_db.py

│   ├── pyspark\_project\_batch.py

│   ├── pyspark\_project\_deletion\_batch.py

│   ├── pyspark\_project\_pagination\_batch.py

│   ├── pyspark\_project\_rollup.py

│   ├── pyspark\_project\_wo\_pagination.py

│   ├── pyspark\_started\_inProgress\_programdashboard.py

│   ├── pyspark\_submitted\_programdashboard.py

│   └── udf\_func.py

├── python3 -> /usr/bin/python3

├── release-notes

│   └── 6.0.0.md

├── requirements.txt

├── run.sh

├── run\_program.sh

├── run\_weekly.sh

├── shell\_script\_config

├── survey

│   ├── ml\_survey\_evidence\_faust-data

│   ├── ml\_survey\_faust-data

│   ├── py\_survey\_batch\_del\_update.py

│   ├── py\_survey\_evidence\_streaming.py

│   ├── py\_survey\_evidence\_streaming\_batch\_refreshment.py

│   ├── py\_survey\_streaming.py

│   ├── py\_survey\_streaming\_batch\_refreshment.py

│   ├── pyspark\_survey\_rollup.py

│   └── pyspark\_survey\_status.py

├── trust\_review\_scripts

│   ├── Trust Review Report.pdf

│   ├── active\_users.py

│   ├── config.sample

│   └── ml\_submissions\_unique\_users.py

└── urgent\_data\_metrics

&#x20;   └── imp\_project\_metrics.py

\


### Module details

* back-up\_reports\_configs - In this folder, we store old reports that are no longer in use, solely for reference purposes.
* cloud\_storage - Within this directory, we maintain the "Cloud" class. This class is utilized in scripts to facilitate the transmission of data or files to the cloud.
* hp\_reports\_metrics - Within this folder, we have scripts dedicated to generating CSV files specifically for program, solution, and district metrics.
* lib - Within this folder, we have scripts dedicated to generating and pussing logs to MongoDB
* manual\_report\_scripts - Within this folder, we have scripts dedicated to generating data related to observations.
* migrations - Within this folder, we have JSON data and script related to report creations.
* observations - Inside this directory, you can find both real-time and batch scripts intended for handling observations.
* projects - Inside this directory, you can find batch scripts intended for handling projects.
* release-notes -  In this folder, we store documentation detailing the necessary steps and tasks to be carried out for deployment.
* survey - Inside this directory, you can find both real-time and batch scripts intended for handling Survey.
* trust\_review\_scripts -Within this folder, you can find scripts designed to provide metrics relevant to Trust review meetings.
* config.sample - This file stores all the essential variables needed for our scripts.
* druid\_data\_product\_query\_config.txt -This file contains the necessary URLs (CURLs) responsible for updating the program dashboard's CSV-related data.
* requirements.txt - This file includes a list of necessary packages required for the successful execution of all our scripts.
* run.sh - This script outlines the sequence and instructions for running our batch scripts in the intended order.
* run\_program.sh - This script outlines the sequence and instructions for running selected scripts in the intended order.
* shell\_script\_config.sample - This file stores all the essential variables needed for our .sh files.
