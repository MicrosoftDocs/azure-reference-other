---
title: Example log table queries for AZKVAuditLogs
description:  Example queries for AZKVAuditLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AZKVAuditLogs table


### Are there any failures?  


Count of failed keyvault requests by status code.  

```query
AZKVAuditLogs
| where HttpStatusCode >= 300 and not(OperationName == "Authentication" and HttpStatusCode == 401)
| summarize count() by RequestUri, ResultSignature, _ResourceId
```



### Are there any slow requests?  


List of keyvault requests taking longer than 1 second.  

```query
let threshold=1000;
AZKVAuditLogs
| where DurationMs > threshold
| summarize count() by OperationName, _ResourceId

```



### How active has this KeyVault been?  


Line chart showing trend of KeyVault requests volume, per operation over time.  

```query
AZKVAuditLogs
| summarize count() by bin(TimeGenerated, 1h), OperationName // Aggregate by hour
| render timechart

```



### How fast is this KeyVault serving requests?  


Line chart showing trend of request duration over time using different aggregations.  

```query
AZKVAuditLogs
| summarize avg(DurationMs) by RequestUri, bin(TimeGenerated, 1h) // requestUri_s contains the URI of the request
| render timechart

```



### What changes occurred last month?  


Lists all update and patch requests from the last 30 days.  

```query
AZKVAuditLogs
| where TimeGenerated > ago(30d)
| where OperationName == "VaultPut" or OperationName == "VaultPatch"
| sort by TimeGenerated desc

```



### Who is calling this KeyVault?  


List of callers identified by their IP address with their request count.  

```query
AZKVAuditLogs
| summarize count() by CallerIpAddress

```

