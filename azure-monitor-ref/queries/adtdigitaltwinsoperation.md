---
title: Example log table queries for ADTDigitalTwinsOperation
description:  Example queries for ADTDigitalTwinsOperation log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ADTDigitalTwinsOperation table


### DigitalTwin Error Summary  


List of all DigitalTwin call errors.  

```query
ADTDigitalTwinsOperation
| where ResultType != 'Success'
```



### DigitalTwin API Usage  


Count of DigitalTwin APIs by type (read, write and delete).  

```query
ADTDigitalTwinsOperation
| summarize count() by OperationName
| render piechart
```

