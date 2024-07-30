---
title: Example log table queries for AMSKeyDeliveryRequests
description:  Example queries for AMSKeyDeliveryRequests log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AMSKeyDeliveryRequests table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Key delivery successful request count by key type  


Summarizes the count of successful key delivery requests by different key types.  

```query
AMSKeyDeliveryRequests
| where ResultType == "Succeeded"
| summarize Count = count() by KeyType
```



### Key delivery failed requests  


Lists the details of failed key delivery requests.  

```query
AMSKeyDeliveryRequests
| where ResultType != "Succeeded"
| project KeyId, PolicyName, ResultSignature, StatusMessage, _ResourceId
| limit 100
```



### Key delivery requests latency at 95 and 99 percentiles  


Estimates the key delivery requests latency at 95th and 99th percentiles.  

```query
AMSKeyDeliveryRequests
| summarize percentiles(DurationMs, 95, 99)
```

