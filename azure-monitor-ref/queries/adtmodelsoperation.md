---
title: Example log table queries for ADTModelsOperation
description:  Example queries for ADTModelsOperation log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ADTModelsOperation table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Model Error Summary  


List of all Model call errors.  

```query
ADTModelsOperation
| where ResultType != 'Success'
```



### Model API Usage  


Count of Model APIs by type (read, write and delete).  

```query
ADTModelsOperation
| summarize count() by OperationName
| render piechart
```

