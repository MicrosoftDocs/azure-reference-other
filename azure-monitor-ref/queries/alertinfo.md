---
title: Example log table queries for AlertInfo
description:  Example queries for AlertInfo log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AlertInfo table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Alerts by MITRE ATT&CK technique  


List number of alerts by MITRE ATT&CK technique in descending order.  

```query
AlertInfo
| where isnotempty(AttackTechniques)
| mvexpand todynamic(AttackTechniques) to typeof(string)
| summarize AlertCount = dcount(AlertId) by AttackTechniques
| sort by AlertCount desc
```

