---
title: Example log table queries for EGNSuccessfulMqttConnections
description:  Example queries for EGNSuccessfulMqttConnections log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the EGNSuccessfulMqttConnections table


### Session connections query  


Connections report by session names.  

```query
EGNSuccessfulMqttConnections
| summarize count() by SessionName
```

