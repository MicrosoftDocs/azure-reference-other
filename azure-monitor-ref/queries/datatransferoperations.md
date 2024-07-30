---
title: Example log table queries for DataTransferOperations
description:  Example queries for DataTransferOperations log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the DataTransferOperations table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Discovered object  


Find discovered objects, or if transfer started.  

```query
DataTransferOperations
| where Status == "SenderProcessing"
| limit 100
```



### Terminal object state  


Find objects that have been completed. Can be used to find if transfer completed successfully or in error state.  

```query
DataTransferOperations 
| where Status == "Rejected"
    or Status == "Delivered"
    or Status == "Failed"
| limit 100
```

