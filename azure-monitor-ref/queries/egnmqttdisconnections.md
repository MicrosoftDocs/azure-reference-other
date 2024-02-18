---
title: Example log table queries for EGNMqttDisconnections
description:  Example queries for EGNMqttDisconnections log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the EGNMqttDisconnections table


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

