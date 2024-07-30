---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: Microsoft.Network/networkManagers, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`ConnectivityConfigurationChange` |Connectivity Configuration Change |[AVNMConnectivityConfigurationChange](/azure/azure-monitor/reference/tables/avnmconnectivityconfigurationchange)<p>Includes logs related to application or removal of connectivity configuration, on network resources like a virtual network.|Yes|No|[Queries](/azure/azure-monitor/reference/queries/avnmconnectivityconfigurationchange)|Yes |
|`NetworkGroupMembershipChange` |Network Group Membership Change |[AVNMNetworkGroupMembershipChange](/azure/azure-monitor/reference/tables/avnmnetworkgroupmembershipchange)<p>Includes changes to network group membership of network resources like a virtual network.|Yes|No|[Queries](/azure/azure-monitor/reference/queries/avnmnetworkgroupmembershipchange)|Yes |
|`RuleCollectionChange` |Rule Collection Change |[AVNMRuleCollectionChange](/azure/azure-monitor/reference/tables/avnmrulecollectionchange)<p>Include logs related to application or removal of rule collections, on network resources like a virtual network or a subnet.|Yes|No|[Queries](/azure/azure-monitor/reference/queries/avnmrulecollectionchange)|Yes |