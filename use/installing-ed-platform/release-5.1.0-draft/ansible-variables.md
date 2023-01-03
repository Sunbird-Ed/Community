# Ansible Variables

### Overview <a href="#overview" id="overview"></a>

Ansible is the configuration management system used in Sunbird. The infrastructure setup, deployment of services and other configurations is handled primarily through ansible.

#### Updating the Private Repository with Hosts and Variables <a href="#updating-the-private-repository-with-hosts-and-variables" id="updating-the-private-repository-with-hosts-and-variables"></a>

Use the following git commands sequentially to clone and update your private GitHub repository -

```bash
git clone https://github.com/project-sunbird/sunbird-devops
cd sunbird-devops
git checkout tags/release-5.1.0 -b release-5.1.0
```

* Copy the directory `sunbird-devops/private_repo/ansible` to your private repo
* Update the files **common.yml**, **hosts**, and **secrets.yml** under **Core**, **KnowledgePlatform** and **DataPipeline** directories. After updating, push them to your private repo branch
* Your private repo structure starting from the root path should be exactly as shown below

```bash
  ansible
└── inventory
    └── dev
        ├── Core
        │   ├── common.yml
        │   ├── hosts
        │   └── secrets.yml
        ├── DataPipeline
        │   ├── common.yml
        │   ├── hosts
        │   └── secrets.yml
        └── KnowledgePlatform
            ├── common.yml
            ├── hosts
            └── secrets.yml
```

**Neo4j download and upload to object storage**

* Neo4j community artifact needs to be downloaded from neo4j official website(only neo4j 3.4 and below is supported)
* Upload downloaded artifact to `cloud_storage_artifacts_bucketname`&#x20;
* Update `neo4j_zip` variable with artifact name `Eg: neo4j-community-3.3.9-unix.tar.gz`

> Note:
>
> * The ansible inventory setup is a must before we can start to run jobs from the **Provision**, **ArtifactUpload** and **Deploy** directory in Jenkins. The **Build** directory on Jenkins does not depend on the ansible variables
> * It is highly recommended that you complete the ansible inventory updates before proceeding further

#### List of Servers with their Ansible Group Names <a href="#list-of-servers-with-their-ansible-group-names" id="list-of-servers-with-their-ansible-group-names"></a>

| Module                    | Servers                                                                              | Service               | Ansible Group Names                                                                                                                                                             |
| ------------------------- | ------------------------------------------------------------------------------------ | --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Build and Deploy          | Server-1                                                                             | Jenkins Master        |                                                                                                                                                                                 |
| Databases                 | Server-2                                                                             | Cassandra             | cassandra-1, lp-cassandra, dp-cassandra, core-cassandra, report-cassandra, cassandra-node-1, cassandra                                                                          |
| Postgres                  | postgresql-master-1, postgresql-master, postgres                                     |                       |                                                                                                                                                                                 |
| Application Elasticsearch | es-1, composite-search-cluster, core-es-1, core-es, es-backup, es                    |                       |                                                                                                                                                                                 |
| Neo4j                     | learning-neo4j-node1, learning-neo4j-cluster                                         |                       |                                                                                                                                                                                 |
| Mongo                     | mongo\_master, mongo                                                                 |                       |                                                                                                                                                                                 |
| Knowledge Platform        | Server-3                                                                             | Redis                 | redis1, redis, redis-ps, redisall, lp-redis, lp-redis-ps, dp-redis, lms-redis, redis-exporter-targets                                                                           |
| Zookeeper                 | processing-cluster-zookeepers, ingestion-cluster-zookeeper, raw-zookeeper, zookeeper |                       |                                                                                                                                                                                 |
| Kafka                     | processing-cluster-kafka, ingestion-cluster-kafka, kafka-1, kafka                    |                       |                                                                                                                                                                                 |
| Data Pipeline             | Server-4                                                                             | Spark                 | spark                                                                                                                                                                           |
| Kafka Indexer (Logstash)  | kafka-indexer                                                                        |                       |                                                                                                                                                                                 |
| InfluxDB                  | influxdb                                                                             |                       |                                                                                                                                                                                 |
| Keycloak                  | keycloak-1, keycloak                                                                 |                       |                                                                                                                                                                                 |
| Yarn                      | Server-5                                                                             | Yarn Master and Slave | yarn-master, yarn-slave, yarn                                                                                                                                                   |
| Learning                  | learning1, learning, learningall                                                     |                       |                                                                                                                                                                                 |
| Other Services            | Server-6                                                                             | Druid                 | druid-postgres, raw-coordinator, raw-overlord, raw-broker, raw-historical, raw-middlemanager, raw-graphite, rollup-coordinator, dp-druid-broker, broker, coordinator, druid-raw |
| Logs Elasticsearch        | log-es-1, log-es-backup, log-es                                                      |                       |                                                                                                                                                                                 |
|                           |                                                                                      |                       |                                                                                                                                                                                 |

\\
