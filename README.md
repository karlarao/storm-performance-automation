# Storm Performance Experiment Tools

## Introduction
This suite contains tools to run performance experiments on WASB and ADLS using Apache Storm. The Storm spout emits a randomly generated record of fixed size. The bolt writes to storage and ACKs the tuple. Once all executor threads complete work, the topology is killed. Results for each worker process are stored on the respective nodes.

## Prequisites/Setup
1. Create a HDInsight cluster of desired size.
2. Fork and clone this repository so you have a local copy.
3. Install the following jar from the /lib directory of this repo to your local maven repository.
```mvn -q install:install-file -Dfile=lib/eventhubs/eventhubs-storm-spout-0.9.3-jar-with-dependencies.jar -DgroupId=com.microsoft.eventhubs -DartifactId=eventhubs-storm-spout -Dversion=0.9.3 -Dpackaging=jar```
4. Build from root folder ```mvn clean package```