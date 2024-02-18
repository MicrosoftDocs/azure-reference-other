---
title: Example log table queries for ADXIngestionBatching
description:  Example queries for ADXIngestionBatching log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ADXIngestionBatching table


### Ingestion batching size  


Track ingestion batch size timechart  

```query
ADXIngestionBatching
| where TimeGenerated > ago(1d)
| summarize sum(BatchSizeBytes) by Database, Table, bin(TimeGenerated, 10m)
| render timechart
```



### Ingestion batching summary  


Ingestion batching summary (by database, table and type).  

```query
ADXIngestionBatching
| where TimeGenerated > ago(1d)
| summarize count() by Database, Table, BatchingType, bin(TimeGenerated, 10m)

```



### Ingestion batching duration timechart  


Track ingestion batching duration timechart.  

```query
ADXIngestionBatching
| where TimeGenerated > ago(1d)
| summarize sum(BatchTimeSeconds) by Database, Table, bin(TimeGenerated, 10m)
| render timechart
```

