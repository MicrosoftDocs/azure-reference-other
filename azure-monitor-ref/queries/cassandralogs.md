---
title: Example log table queries for CassandraLogs
description:  Example queries for CassandraLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the CassandraLogs table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Cassandra logs  


Cassandra logs for a specific node, sorted by time (latest logs shown first).  

```query
let nodeIPAddress = "10.0.0.0"; // Replace with your node IP address
CassandraLogs
| where AddressIP == nodeIPAddress
| sort by TimeGenerated desc
```



### Cassandra errors or warnings  


Error or warning logs from Cassandra, sorted by time (latest logs shown first).  

```query
CassandraLogs
| where Level == "ERROR" or Level == "WARN"
| project TimeGenerated, Level, AddressIp, ThreadName, ThreadId, SourceFile, SourceLine, Message, Exception, EventProduct, EventCategory, EventType
| sort by TimeGenerated desc
```

