# Update Ansible Variables

Ansible is the configuration management system used in Sunbird. The infrastructure setup, deployment of services and other configurations is handled primarily through ansible.**Updating the Private Repository with Hosts and Variables**Execute the following commands in your local to clone the private repo template and update your private GitHub repository -git clone https://github.com/project-sunbird/sunbird-devopscd sunbird-devopsgit checkout tags/release-6.0.0 -b release-6.0.0

* Copy the directory `sunbird-devops/private_repo/ansible` to your private repo local workspace
* Run the `key-generate.sh` script located under `ansible/inventory/dev` folder. The script will ask for the ansible vault password. Enter the same vault password that you used in the Jenkins setup stage. The script will generate many private key files and they will be encrypted with the vault password. Deployments will fail if keys are not encrypted.
* Update the files **common.yml**, **hosts**, and **secrets.yml** under **Core**, **KnowledgePlatform** and **DataPipeline** directories. After updating, push them to your private repo branch
* Your private repo structure starting from the root path should be as shown below

ansible└── inventory└── dev├── Core│ ├── common.yml│ ├── hosts│ └── secrets.yml├── Kubernetes│ ├── common.yml (soft link to Core directory files)│ ├── hosts. (soft link to Core directory files)│ └── secrets.yml (soft link to Core directory files)├── DataPipeline│ ├── common.yml│ ├── hosts│ └── secrets.yml└── KnowledgePlatform├── common.yml├── hosts└── secrets.yml**Neo4j download and upload to object storage**

* Neo4j community artifact needs to be downloaded from neo4j official website [http://dist.neo4j.org/neo4j-community-3.3.9-unix.tar.gz](http://dist.neo4j.org/neo4j-community-3.3.9-unix.tar.gz) (only Neo4j 3.4 and below is supported)
* Upload downloaded artifact to `cloud_storage_artifacts_bucketname`
* Update `neo4j_zip` variable with artifact name `Eg: neo4j-community-3.3.9-unix.tar.gz`

> Note:
>
> * The ansible inventory setup is a must before we can start to run jobs from the **Provision**, **ArtifactUpload** and **Deploy** directory in Jenkins. The **Build** directory on Jenkins does not depend on the ansible variables
> * It is highly recommended that you complete the ansible inventory updates before proceeding further

**List of Servers with their Ansible Group Names**

| Module             | Servers  | Service                   | Ansible Group Names                                                                                                                                                             |
| ------------------ | -------- | ------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Build and Deploy   | Server-1 | Jenkins Master            | ​                                                                                                                                                                               |
| Databases          | Server-2 | Cassandra                 | cassandra-1, lp-cassandra, dp-cassandra, core-cassandra, report-cassandra, cassandra-node-1, cassandra                                                                          |
| ​                  | ​        | Postgres                  | postgresql-master-1, postgresql-master, postgres                                                                                                                                |
| ​                  | ​        | Application Elasticsearch | es-1, composite-search-cluster, core-es-1, core-es, es-backup, es                                                                                                               |
| ​                  | ​        | Neo4j                     | learning-neo4j-node1, learning-neo4j-cluster                                                                                                                                    |
| ​                  | ​        | Mongo                     | mongo\_master, mongo                                                                                                                                                            |
| Knowledge Platform | Server-3 | Redis                     | redis1, redis, redis-ps, redisall, lp-redis, lp-redis-ps, dp-redis, lms-redis, redis-exporter-targets                                                                           |
| ​                  | ​        | Zookeeper                 | processing-cluster-zookeepers, ingestion-cluster-zookeeper, raw-zookeeper, zookeeper                                                                                            |
| ​                  | ​        | Kafka                     | processing-cluster-kafka, ingestion-cluster-kafka, kafka-1, kafka                                                                                                               |
| Data Pipeline      | Server-4 | Spark                     | spark                                                                                                                                                                           |
| ​                  | ​        | Kafka Indexer (Logstash)  | kafka-indexer                                                                                                                                                                   |
| ​                  | ​        | InfluxDB                  | influxdb                                                                                                                                                                        |
| ​                  | ​        | Keycloak                  | keycloak-1, keycloak                                                                                                                                                            |
| Learning           | Server-5 | Learning                  | learning1, learning, learningall                                                                                                                                                |
| ​                  | ​        | Graylog                   | graylog-1, graylog                                                                                                                                                              |
| Druid              | Server-6 | Druid                     | druid-postgres, raw-coordinator, raw-overlord, raw-broker, raw-historical, raw-middlemanager, raw-graphite, rollup-coordinator, dp-druid-broker, broker, coordinator, druid-raw |
| ​                  | ​        | Logs Elasticsearch        | log-es-1, log-es-backup, log-es                                                                                                                                                 |
