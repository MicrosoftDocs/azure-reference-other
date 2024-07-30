---
title: Example log table queries for ADTDataHistoryOperation
description:  Example queries for ADTDataHistoryOperation log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ADTDataHistoryOperation table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Data History operation failure logs  


Failed operation events logged when data history messages are sent to the time series database.  

```query
ADTDataHistoryOperation
| where ResultType == "Failure"
| take 100

```



### Data History egress latency  


Delivery latency of data history messages sent to the time series database.  

```query
ADTDataHistoryOperation
| where OperationName == "Microsoft.DigitalTwins/digitalTwinsInstances/datahistory/messages/send/action"
| summarize percentile(DurationMs, 99) by bin(TimeGenerated, 5m)

```

