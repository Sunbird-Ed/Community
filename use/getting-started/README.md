# Getting Started - Setup

### 🚀 Overview

From 7.5 release, Sunbird-ED has moved from a hybrid deployment model to a fully Kubernetes-native architecture. Previously, deployments were managed using Jenkins, Ansible, and Helm, with services split between Kubernetes and traditional VMs. Components like Neo4j, Cassandra, Redis, Postgres, Elasticsearch, Keycloak, Druid, Kafka, and Spark ran on VMs, requiring additional orchestration and configuration.<br>

With the new [Sunbird-ED Installer](https://github.com/project-sunbird/sunbird-ed-installer):

* ✅ All services run natively on Kubernetes.
* ✅ Easier deployment across multiple cloud providers.
* ✅ All building blocks are bundled and modular.
* ✅ Simplified installation and maintenance experience.

This makes it easier to spin up, manage, and scale Sunbird-ED environments.

