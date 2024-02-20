---
title: Example log table queries for KubeEvents
description:  Example queries for KubeEvents log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the KubeEvents table


### Kubernetes events  


Lists all the Kubernetes events.  

```query
KubeEvents
| where TimeGenerated > ago(7d) 
| where not(isempty(Namespace))
| top 200 by TimeGenerated desc
```



### Find In KubeEvents  


Find in KubeEvents to search for a specific value in the KubeEvents table./nNote that this query requires updating the \<SeachValue\> parameter to produce results  

```query
// This query requires a parameter to run. Enter value in SearchValue to find in table.
let SearchValue =  "<SearchValue>";//Please update term you would like to find in the table.
KubeEvents
| where * contains tostring(SearchValue)
| take 1000
```

