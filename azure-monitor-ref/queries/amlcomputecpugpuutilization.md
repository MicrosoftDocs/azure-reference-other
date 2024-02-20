---
title: Example log table queries for AmlComputeCpuGpuUtilization
description:  Example queries for AmlComputeCpuGpuUtilization log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AmlComputeCpuGpuUtilization table


### Plot compute cluster utilization  


Plot recent compute cluster CPU utilization over time for specific cluster.  

```query
AmlComputeCpuGpuUtilization
| join kind = inner (AmlComputeJobEvent
        | where  NodeId!="" and EventType =="JobSucceeded"
        | project NodeId, ClusterName)
    on NodeId 
| project TimeGenerated, todecimal(Utilization),  ClusterName, DeviceType
| where ClusterName=="Cpu-cluster" and DeviceType=="CPU"
| limit 100
| render timechart   
```

