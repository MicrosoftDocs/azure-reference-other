---
title: Example log table queries for UCDOAggregatedStatus
description:  Example queries for UCDOAggregatedStatus log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the UCDOAggregatedStatus table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Content distribution in Gigabytes  


Get the content distribution in Gigabytes for all the devices.  

```query
UCDOAggregatedStatus 
|extend   
LanGB =  todouble(BytesFromPeers)/pow(1024,3),
GroupGB = todouble(BytesFromGroupPeers)/pow(1024,3),
NonPeerGB = todouble(BytesFromCDN)/pow(1024,3)
|project 
Content = ContentType,
LanGB,
GroupGB, 
NonPeerGB, 
DeviceCount
```

