---
title: Example log table queries for SucceededIngestion
description:  Example queries for SucceededIngestion log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the SucceededIngestion table


### Succeeded ingestions  


How many succeeded ingestions accrued (per database, table).  

```query
SucceededIngestion
| parse _ResourceId with * "providers/microsoft.kusto/clusters/" cluster_name // Get the cluster name from the ResourceId string
| summarize count() by bin(TimeGenerated, 1h), cluster_name, Database, Table
```



### Succeeded ingestions timechart  


How many succeeded ingestions accrued (timechart).  

```query
SucceededIngestion 
| summarize count() by bin(TimeGenerated, 1h) 
| render timechart 
```

