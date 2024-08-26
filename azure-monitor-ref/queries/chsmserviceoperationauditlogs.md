---
title: Example log table queries for CHSMServiceOperationAuditLogs
description:  Example queries for CHSMServiceOperationAuditLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 08/26/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the CHSMServiceOperationAuditLogs table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Are there any slow requests?  


List of Cloud HSM requests taking longer than 1 second.  

```query
let threshold=1000;
CHSMServiceOperationAuditLogs
| where DurationMs > threshold
| summarize count() by OperationName, _ResourceId
```



### How active has this Cloud HSM been?  


Line chart showing trend of Cloud HSM requests volume, per operation over time.  

```query
CHSMServiceOperationAuditLogs
| summarize count() by bin(TimeGenerated, 1h), OperationName // Aggregate by hour
| render timechart
```



### Are there any failures?  


Count of failed requests by request type  

```query
CHSMServiceOperationAuditLogs
| where ResultType == "Failure"
| summarize count() by ResultSignature, _ResourceId
```



### Who is calling this Cloud HSM?  


List of callers identified by their IP address with their request count.  

```query
CHSMServiceOperationAuditLogs
| summarize count() by CallerIpAddress
```

