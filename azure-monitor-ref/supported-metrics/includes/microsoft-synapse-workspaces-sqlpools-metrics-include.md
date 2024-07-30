---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.Synapse/workspaces/sqlPools, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|SQL dedicated pool|**Active queries**<br><br>The active queries. Using this metric unfiltered and unsplit displays all active queries running on the system |`ActiveQueries` |Count |Total |`IsUserDefined`|PT1M |No|
|SQL dedicated pool|**Adaptive cache hit percentage**<br><br>Measures how well workloads are utilizing the adaptive cache. Use this metric with the cache hit percentage metric to determine whether to scale for additional capacity or rerun workloads to hydrate the cache |`AdaptiveCacheHitPercent` |Percent |Maximum, Minimum, Average |\<none\>|PT1M |No|
|SQL dedicated pool|**Adaptive cache used percentage**<br><br>Measures how well workloads are utilizing the adaptive cache. Use this metric with the cache used percentage metric to determine whether to scale for additional capacity or rerun workloads to hydrate the cache |`AdaptiveCacheUsedPercent` |Percent |Maximum, Minimum, Average |\<none\>|PT1M |No|
|SQL dedicated pool|**Connections**<br><br>Count of Total logins to the SQL pool |`Connections` |Count |Total |`Result`|PT1M |Yes|
|SQL dedicated pool|**Connections blocked by firewall**<br><br>Count of connections blocked by firewall rules. Revisit access control policies for your SQL pool and monitor these connections if the count is high |`ConnectionsBlockedByFirewall` |Count |Total |\<none\>|PT1M |No|
|SQL dedicated pool|**CPU used percentage**<br><br>CPU utilization across all nodes in the SQL pool |`CPUPercent` |Percent |Maximum, Minimum, Average |\<none\>|PT1M |No|
|SQL dedicated pool|**DWU limit**<br><br>Service level objective of the SQL pool |`DWULimit` |Count |Maximum, Minimum, Average |\<none\>|PT1M |No|
|SQL dedicated pool|**DWU used**<br><br>Represents a high-level representation of usage across the SQL pool. Measured by DWU limit * DWU percentage |`DWUUsed` |Count |Maximum, Minimum, Average |\<none\>|PT1M |No|
|SQL dedicated pool|**DWU used percentage**<br><br>Represents a high-level representation of usage across the SQL pool. Measured by taking the maximum between CPU percentage and Data IO percentage |`DWUUsedPercent` |Percent |Maximum, Minimum, Average |\<none\>|PT1M |No|
|SQL dedicated pool|**Local tempdb used percentage**<br><br>Local tempdb utilization across all compute nodes - values are emitted every five minute |`LocalTempDBUsedPercent` |Percent |Maximum, Minimum, Average |\<none\>|PT1M |No|
|SQL dedicated pool|**Memory used percentage**<br><br>Memory utilization across all nodes in the SQL pool |`MemoryUsedPercent` |Percent |Maximum, Minimum, Average |\<none\>|PT1M |No|
|SQL dedicated pool|**Queued queries**<br><br>Cumulative count of requests queued after the max concurrency limit was reached |`QueuedQueries` |Count |Total |`IsUserDefined`|PT1M |No|
|SQL dedicated pool - Workload management|**Workload group active queries**<br><br>The active queries within the workload group. Using this metric unfiltered and unsplit displays all active queries running on the system |`WLGActiveQueries` |Count |Total |`IsUserDefined`, `WorkloadGroup`|PT1M |No|
|SQL dedicated pool - Workload management|**Workload group query timeouts**<br><br>Queries for the workload group that have timed out. Query timeouts reported by this metric are only once the query has started executing (it does not include wait time due to locking or resource waits) |`WLGActiveQueriesTimeouts` |Count |Total |`IsUserDefined`, `WorkloadGroup`|PT1M |No|
|SQL dedicated pool - Workload management|**Workload group allocation by max resource percent**<br><br>Displays the percentage allocation of resources relative to the Effective cap resource percent per workload group. This metric provides the effective utilization of the workload group |`WLGAllocationByEffectiveCapResourcePercent` |Percent |Maximum, Minimum, Average |`IsUserDefined`, `WorkloadGroup`|PT1M |No|
|SQL dedicated pool - Workload management|**Workload group allocation by system percent**<br><br>The percentage allocation of resources relative to the entire system |`WLGAllocationBySystemPercent` |Percent |Maximum, Minimum, Average, Total |`IsUserDefined`, `WorkloadGroup`|PT1M |No|
|SQL dedicated pool - Workload management|**Effective cap resource percent**<br><br>The effective cap resource percent for the workload group. If there are other workload groups with min_percentage_resource > 0, the effective_cap_percentage_resource is lowered proportionally |`WLGEffectiveCapResourcePercent` |Percent |Maximum, Minimum, Average |`IsUserDefined`, `WorkloadGroup`|PT1M |No|
|SQL dedicated pool - Workload management|**Effective min resource percent**<br><br>The effective min resource percentage setting allowed considering the service level and the workload group settings. The effective min_percentage_resource can be adjusted higher on lower service levels |`WLGEffectiveMinResourcePercent` |Percent |Minimum, Maximum, Average, Total |`IsUserDefined`, `WorkloadGroup`|PT1M |No|
|SQL dedicated pool - Workload management|**Workload group queued queries**<br><br>Cumulative count of requests queued after the max concurrency limit was reached |`WLGQueuedQueries` |Count |Total |`IsUserDefined`, `WorkloadGroup`|PT1M |No|