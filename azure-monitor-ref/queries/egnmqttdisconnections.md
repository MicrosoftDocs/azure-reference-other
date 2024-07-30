---
title: Example log table queries for EGNMqttDisconnections
description:  Example queries for EGNMqttDisconnections log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the EGNMqttDisconnections table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Disconnections reason query  


Disconnections report by reasons.  

```query
EGNMqttDisconnections
| summarize count() by ResultSignature
```



### Session disconnections query  


Disconnections report by session names.  

```query
EGNMqttDisconnections
| summarize count() by SessionName
```

