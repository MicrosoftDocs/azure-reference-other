---
ms.service: azure-monitor
ms.topic: include
ms.date: 05/06/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.ManagedNetworkFabric/networkDevices, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`BfdStateUpdates` |Bi-Directional Forwarding Detection Updates ||No|No||Yes |
|`ComponentStateUpdates` |Component State Updates |[MNFDeviceUpdates](/azure/azure-monitor/reference/tables/mnfdeviceupdates)<p>Components state updates representing the status changes of ethernet ports, power supply units, fan modules, chassis and device software.|Yes|No|[Queries](/azure/azure-monitor/reference/queries/mnfdeviceupdates)|Yes |
|`InterfaceStateUpdates` |Interface State Updates ||No|No||Yes |
|`InterfaceVxlanUpdates` |Interface Vxlan Updates ||No|No||Yes |
|`NetworkInstanceBgpNeighborUpdates` |BGP Neighbor Updates ||No|No||Yes |
|`NetworkInstanceUpdates` |Network Instance Updates ||No|No||Yes |
|`SystemSessionHistoryUpdates` |System Session History Updates ||No|No||Yes |
|`SystemStateMessageUpdates` |System State Message Updates |[MNFSystemStateMessageUpdates](/azure/azure-monitor/reference/tables/mnfsystemstatemessageupdates)<p>System state message update events in the Nexus network fabric devices.|Yes|No|[Queries](/azure/azure-monitor/reference/queries/mnfsystemstatemessageupdates)|Yes |