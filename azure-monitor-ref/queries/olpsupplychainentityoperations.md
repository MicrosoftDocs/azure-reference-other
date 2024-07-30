---
title: Example log table queries for OLPSupplyChainEntityOperations
description:  Example queries for OLPSupplyChainEntityOperations log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the OLPSupplyChainEntityOperations table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Count of successful warehouse delete requests  


Evaluates the count of successful warehouse delete requests.  

```query
SupplyChainEntityOperationLogs
| where RequestMethod == "DELETE" and OperationName == "Microsoft.OpenLogisticsPlatform/workspace/warehouses/delete" and HttpStatusCode == 200
| summarize Count = count() by RequestId
```

