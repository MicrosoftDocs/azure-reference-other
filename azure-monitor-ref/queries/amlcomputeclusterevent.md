---
title: Example log table queries for AmlComputeClusterEvent
description:  Example queries for AmlComputeClusterEvent log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AmlComputeClusterEvent table


### Get cluster events for clusters for specific VM size  


Get top 100 cluster events for clusters where the VM size is Standard_D1_V2.  

```query
AmlComputeClusterEvent
| where VmSize == "STANDARD_D1_V2"
| project  ClusterName, InitialNodeCount, MaximumNodeCount, QuotaAllocated, QuotaUtilized
| limit 100
```



### Get number of running nodes  


Get number of running nodes across workspaces and clusters.  

```query
AmlComputeClusterEvent
| summarize avgRunningNodes=avg(TargetNodeCount), maxRunningNodes=max(TargetNodeCount) by Workspace=tostring(split(_ResourceId, "/")[8]), ClusterName, ClusterType, VmSize, VmPriority
| limit 100
```



### Graph of Running and Idle Node instances  


Graph of Running and Idle Node instances.  

```query
AmlComputeClusterEvent
| project TimeGenerated, WorkspaceName=split(_ResourceId, "/")[-1], ClusterName, ClusterType, VmSize, VmPriority, 
  InitialNodeCount , IdleNodeCount, RunningNodeCount, PreparingNodeCount, MinimumNodeCount, MaximumNodeCount , CurrentNodeCount, TargetNodeCount 
|summarize round(sum(RunningNodeCount),1), round(sum(IdleNodeCount),1) by  Hourly=bin(TimeGenerated, 60m) 
| render timechart
```

