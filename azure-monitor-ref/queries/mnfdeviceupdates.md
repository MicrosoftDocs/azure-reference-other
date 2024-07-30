---
title: Example log table queries for MNFDeviceUpdates
description:  Example queries for MNFDeviceUpdates log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the MNFDeviceUpdates table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Find all entries where value is active  


Components state updates events are projected from devices. This query will list out all logs where value is active.  

```query
MNFDeviceUpdates
| where EventCategory == "ComponentStateUpdates"
| where Properties has "ACTIVE"
| project EventName, EventCategory, DeviceId, TimeGenerated, Properties
| sort by TimeGenerated desc
| limit 100
```



### Find all entries where value is up  


Interface status updates are projected from devices. This query will list out all logs where value is up.  

```query
MNFDeviceUpdates
| where EventCategory == "InterfaceStateUpdates"
| where Properties !has "DOWN"
| project EventName, EventCategory, DeviceId, TimeGenerated, Properties
| sort by TimeGenerated desc
| limit 100
```



### Find all events of the type VxlanVlanToVniVlan  


Interface vxlan updates events are projected from devices. This query will list out all the logs where events is of the type VxlanVlanToVniVlan.  

```query
MNFDeviceUpdates
| where EventCategory == "InterfaceVxlanUpdates"
| where Properties has "VxlanVlanToVniVlan"
| project EventName, EventCategory, DeviceId, TimeGenerated, Properties
| sort by TimeGenerated desc
| limit 100
```



### Find all entries where afisafiname is not of the type L2VPN_EVPN  


Network instance neighbor updates that happened between routers during a BGP communication are listed with types of afisafiname. This is the query to filter the logs where afisafiname is not of the type L2VPN_EVPN.  

```query
MNFDeviceUpdates
| where EventCategory == "NetworkInstanceBgpNeighborUpdates"
| where Properties !has "L2VPN_EVPN"
| project EventName, EventCategory, DeviceId, TimeGenerated, Properties
| sort by TimeGenerated desc
| limit 100
```



### Find all entries where network instance name is of the type workload-mgmt  


Network instance updates events from device will be reported here with different instance name. This query filters all network instances of the type workload-mgmt.  

```query
MNFDeviceUpdates
| where EventCategory == "NetworkInstanceUpdates"
| where Properties has "WORKLOAD-MGMT"
| project EventName, EventCategory, DeviceId, TimeGenerated, Properties
| sort by TimeGenerated desc
| limit 100
```

