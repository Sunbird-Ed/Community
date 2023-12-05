---
description: How does content get indexed in Elastic Search
---

# Content Indexing Flow

1. Content create, update, publish, retire etc APIs are called and content is updated in Neo4j
2. Neo4j writes these updates to a log file, typically located at `/data/logs/learning_graph_event_neo4j.log`. This file needs to have the right permissions i.e. it needs to be owned by the user neo4j is running as. Usually this is `learning`
3. The logstash service picks up lines from this log and pushes as events into the [dev.learning.graph.events](http://dev.learning.graph.events) topic
4. The search indexer service picks up events from above topic and creates/updates the records in ES
5. The search indexer config affects how the data is inserted
   1. nested.fields affects how certain fields are mapped
   2. restrict.objectTypes - Any records with these object types is not inserted into ES
6. This applies to all the object types stored in Neo4J - Content, Collection, Question, QuestionSet, License, Framework, Channel
