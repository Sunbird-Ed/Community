# How does data flow into Druid

Gets picked up from telemetry topics

Then it goes through these flink jobs before landing into the druid topics

1. ingest router job
2. telemetry extractor
3. pipeline preprocessor
4. denorm
5. druid validator
