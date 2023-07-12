---
title: Supported metrics - Microsoft.ContainerService/managedClusters
description: Reference for Microsoft.ContainerService/managedClusters metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.ContainerService/managedClusters  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.ContainerService/managedClusters resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Inflight Requests<p><p>Maximum number of currently used inflight requests on the apiserver per request kind in the last second |`apiserver_current_inflight_requests` |Count |Average |requestKind |No|
|Cluster Health<p><p>Determines whether or not cluster autoscaler will take action on the cluster |`cluster_autoscaler_cluster_safe_to_autoscale` |Count |Average |No Dimensions |No|
|Scale Down Cooldown<p><p>Determines if the scale down is in cooldown - No nodes will be removed during this timeframe |`cluster_autoscaler_scale_down_in_cooldown` |Count |Average |No Dimensions |No|
|Unneeded Nodes<p><p>Cluster auotscaler marks those nodes as candidates for deletion and are eventually deleted |`cluster_autoscaler_unneeded_nodes_count` |Count |Average |No Dimensions |No|
|Unschedulable Pods<p><p>Number of pods that are currently unschedulable in the cluster |`cluster_autoscaler_unschedulable_pods_count` |Count |Average |No Dimensions |No|
|Total number of available cpu cores in a managed cluster<p><p>Total number of available cpu cores in a managed cluster |`kube_node_status_allocatable_cpu_cores` |Count |Average |No Dimensions |No|
|Total amount of available memory in a managed cluster<p><p>Total amount of available memory in a managed cluster |`kube_node_status_allocatable_memory_bytes` |Bytes |Average |No Dimensions |No|
|Statuses for various node conditions<p><p>Statuses for various node conditions |`kube_node_status_condition` |Count |Average |condition, status, status2, node |No|
|Number of pods by phase<p><p>Number of pods by phase |`kube_pod_status_phase` |Count |Average |phase, namespace, pod |No|
|Number of pods in Ready state<p><p>Number of pods in Ready state |`kube_pod_status_ready` |Count |Average |namespace, pod, condition |No|
|CPU Usage Millicores<p><p>Aggregated measurement of CPU utilization in millicores across the cluster |`node_cpu_usage_millicores` |MilliCores |Average |node, nodepool |Yes|
|CPU Usage Percentage<p><p>Aggregated average CPU utilization measured in percentage across the cluster |`node_cpu_usage_percentage` |Percent |Average |node, nodepool |Yes|
|Disk Used Bytes<p><p>Disk space used in bytes by device |`node_disk_usage_bytes` |Bytes |Average |node, nodepool, device |Yes|
|Disk Used Percentage<p><p>Disk space used in percent by device |`node_disk_usage_percentage` |Percent |Average |node, nodepool, device |Yes|
|Memory RSS Bytes<p><p>Container RSS memory used in bytes |`node_memory_rss_bytes` |Bytes |Average |node, nodepool |Yes|
|Memory RSS Percentage<p><p>Container RSS memory used in percent |`node_memory_rss_percentage` |Percent |Average |node, nodepool |Yes|
|Memory Working Set Bytes<p><p>Container working set memory used in bytes |`node_memory_working_set_bytes` |Bytes |Average |node, nodepool |Yes|
|Memory Working Set Percentage<p><p>Container working set memory used in percent |`node_memory_working_set_percentage` |Percent |Average |node, nodepool |Yes|
|Network In Bytes<p><p>Network received bytes |`node_network_in_bytes` |Bytes |Average |node, nodepool |Yes|
|Network Out Bytes<p><p>Network transmitted bytes |`node_network_out_bytes` |Bytes |Average |node, nodepool |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->