---
title: Supported metrics - Microsoft.Synapse/workspaces/sqlPools
description: Reference for Microsoft.Synapse/workspaces/sqlPools metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Synapse/workspaces/sqlPools  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Synapse/workspaces/sqlPools resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Active queries<p><p>The active queries. Using this metric unfiltered and unsplit displays all active queries running on the system |`ActiveQueries` |Count |Total |IsUserDefined |No|
|Adaptive cache hit percentage<p><p>Measures how well workloads are utilizing the adaptive cache. Use this metric with the cache hit percentage metric to determine whether to scale for additional capacity or rerun workloads to hydrate the cache |`AdaptiveCacheHitPercent` |Percent |Maximum |No Dimensions |No|
|Adaptive cache used percentage<p><p>Measures how well workloads are utilizing the adaptive cache. Use this metric with the cache used percentage metric to determine whether to scale for additional capacity or rerun workloads to hydrate the cache |`AdaptiveCacheUsedPercent` |Percent |Maximum |No Dimensions |No|
|Connections<p><p>Count of Total logins to the SQL pool |`Connections` |Count |Total |Result |Yes|
|Connections blocked by firewall<p><p>Count of connections blocked by firewall rules. Revisit access control policies for your SQL pool and monitor these connections if the count is high |`ConnectionsBlockedByFirewall` |Count |Total |No Dimensions |No|
|CPU used percentage<p><p>CPU utilization across all nodes in the SQL pool |`CPUPercent` |Percent |Maximum |No Dimensions |No|
|DWU limit<p><p>Service level objective of the SQL pool |`DWULimit` |Count |Maximum |No Dimensions |No|
|DWU used<p><p>Represents a high-level representation of usage across the SQL pool. Measured by DWU limit * DWU percentage |`DWUUsed` |Count |Maximum |No Dimensions |No|
|DWU used percentage<p><p>Represents a high-level representation of usage across the SQL pool. Measured by taking the maximum between CPU percentage and Data IO percentage |`DWUUsedPercent` |Percent |Maximum |No Dimensions |No|
|Local tempdb used percentage<p><p>Local tempdb utilization across all compute nodes - values are emitted every five minute |`LocalTempDBUsedPercent` |Percent |Maximum |No Dimensions |No|
|Memory used percentage<p><p>Memory utilization across all nodes in the SQL pool |`MemoryUsedPercent` |Percent |Maximum |No Dimensions |No|
|Queued queries<p><p>Cumulative count of requests queued after the max concurrency limit was reached |`QueuedQueries` |Count |Total |IsUserDefined |No|
|Workload group active queries<p><p>The active queries within the workload group. Using this metric unfiltered and unsplit displays all active queries running on the system |`WLGActiveQueries` |Count |Total |IsUserDefined, WorkloadGroup |No|
|Workload group query timeouts<p><p>Queries for the workload group that have timed out. Query timeouts reported by this metric are only once the query has started executing (it does not include wait time due to locking or resource waits) |`WLGActiveQueriesTimeouts` |Count |Total |IsUserDefined, WorkloadGroup |No|
|Workload group allocation by max resource percent<p><p>Displays the percentage allocation of resources relative to the Effective cap resource percent per workload group. This metric provides the effective utilization of the workload group |`WLGAllocationByEffectiveCapResourcePercent` |Percent |Maximum |IsUserDefined, WorkloadGroup |No|
|Workload group allocation by system percent<p><p>The percentage allocation of resources relative to the entire system |`WLGAllocationBySystemPercent` |Percent |Maximum |IsUserDefined, WorkloadGroup |No|
|Effective cap resource percent<p><p>The effective cap resource percent for the workload group. If there are other workload groups with min_percentage_resource > 0, the effective_cap_percentage_resource is lowered proportionally |`WLGEffectiveCapResourcePercent` |Percent |Maximum |IsUserDefined, WorkloadGroup |No|
|Effective min resource percent<p><p>The effective min resource percentage setting allowed considering the service level and the workload group settings. The effective min_percentage_resource can be adjusted higher on lower service levels |`WLGEffectiveMinResourcePercent` |Percent |Maximum |IsUserDefined, WorkloadGroup |No|
|Workload group queued queries<p><p>Cumulative count of requests queued after the max concurrency limit was reached |`WLGQueuedQueries` |Count |Total |IsUserDefined, WorkloadGroup |No|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->