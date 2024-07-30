---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.NetworkCloud/clusterManagers, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Nexus Cluster|**Cluster Connection Status**<br><br>Tracks changes in the connection status of the Cluster(s) managed by the Cluster Manager. The metric gets a value of 0 when the Cluster is connected and 1 when disconnected. The reason filter describes the connection status itself. |`NexusClusterConnectionStatus` |Count |Average |`clusterName`, `reason`|PT1M |No|
|Nexus Cluster|**Cluster Deploy Requests**<br><br>Number of cluster deploy requests |`NexusClusterDeployClusterRequests` |Count |Average |`clusterVersion`|PT1M |No|
|Nexus Cluster|**Cluster Machine Upgrade**<br><br>Nexus machine upgrade request, successful will have a value of 0 while unsuccessful while have a value of 1. |`NexusClusterMachineUpgrade` |Count |Average |`clusterName`, `clusterVersion`, `result`, `upgradedFromVersion`, `upgradedToVersion`, `upgradeStrategy`|PT1M |No|
|Nexus Cluster|**Cluster Management Bundle Upgrade**<br><br>Nexus Cluster management bundle upgrade, successful will have a value of 0 while unsuccessful while have a value of 1. |`NexusClusterManagementBundleUpgrade` |Count |Average |`clusterName`, `clusterVersion`, `result`, `upgradedFromVersion`, `upgradedToVersion`|PT1M |No|
|Nexus Cluster|**Cluster Runtime Bundle Upgrade**<br><br>Nexus Cluster runtime bundle upgrade, successful will have a value of 0 while unsuccessful while have a value of 1. |`NexusClusterRuntimeBundleUpgrade` |Count |Average |`clusterName`, `clusterVersion`, `result`, `upgradedFromVersion`, `upgradedToVersion`|PT1M |No|