# What are multiple databases used for

### Content Service

* All schema fields except body is stored in Neo4J
* Body, hierarchy is stored in cassandra
* Redis caches the content ids and hierarchy for use by other services
* Content is indexed to Elastic Search

### Search API

* Search API runs off Elastic Search. More details [here](content-indexing-flow.md)
* The compositesearch index is used for the search.
* compositesearch is actually just an alias to an actual ES index. This is done so that if the index crashes, a new index can be built, and the alias can be pointed to the new index

### Cassandra Migrations

Cassandra migrations are stored in this repo -[https://github.com/project-sunbird/sunbird-utils](https://github.com/project-sunbird/sunbird-utils)

Folder - sunbird-cassandra-migration/cassandra-migration/src/main/resources/db/migration/cassandra

### Redis

There are two redis instances running. A metadata redis and a knowledge platform redis

1. metadata redis / db12 : user cache used by DP Jobs
2.
