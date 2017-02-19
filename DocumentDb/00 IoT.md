https://docs.microsoft.com/en-us/azure/documentdb/documentdb-use-cases

IoT use cases commonly share some patterns in how they ingest, process, and store data. First, these systems need to ingest bursts of data from device sensors of various locales. Next, these systems process and analyze streaming data to derive real-time insights. The data is then archived to cold storage for batch analytics.

Microsoft Azure offers rich services that can be applied for IoT use cases including Azure Event Hubs, Azure DocumentDB, Azure Stream Analytics, Azure Notification Hub, Azure Machine Learning, Azure HDInsight, and PowerBI.
(https://docs.microsoft.com/en-us/azure/documentdb/media/documentdb-use-cases/documentdb-iot.png)


Bursts of data can be ingested by Azure Event Hubs as it offers high throughput data ingestion with low latency. Data ingested that needs to be processed for real-time insight can be funneled to Azure Stream Analytics for real-time analytics. Data can be loaded into DocumentDB for adhoc querying. Once the data is loaded into DocumentDB, the data is ready to be queried. The data in DocumentDB can be used as reference data as part of real-time analytics. In addition, data can further be refined and processed by connecting DocumentDB data to HDInsight for Pig, Hive or Map/Reduce jobs. Refined data is then loaded back to DocumentDB for reporting.
(https://github.com/hdinsight/hdinsight-storm-examples/)
