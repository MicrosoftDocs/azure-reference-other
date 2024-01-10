---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.ContainerService/managedClusters, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|API Server (PREVIEW)|**Inflight Requests**<p><p>Maximum number of currently used inflight requests on the apiserver per request kind in the last second |`apiserver_current_inflight_requests` |Count |Total, Average |`requestKind`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |No|
|Cluster Autoscaler (PREVIEW)|**Cluster Health**<p><p>Determines whether or not cluster autoscaler will take action on the cluster |`cluster_autoscaler_cluster_safe_to_autoscale` |Count |Total, Average |\<none\>|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |No|
|Cluster Autoscaler (PREVIEW)|**Scale Down Cooldown**<p><p>Determines if the scale down is in cooldown - No nodes will be removed during this timeframe |`cluster_autoscaler_scale_down_in_cooldown` |Count |Total, Average |\<none\>|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |No|
|Cluster Autoscaler (PREVIEW)|**Unneeded Nodes**<p><p>Cluster auotscaler marks those nodes as candidates for deletion and are eventually deleted |`cluster_autoscaler_unneeded_nodes_count` |Count |Total, Average |\<none\>|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |No|
|Cluster Autoscaler (PREVIEW)|**Unschedulable Pods**<p><p>Number of pods that are currently unschedulable in the cluster |`cluster_autoscaler_unschedulable_pods_count` |Count |Total, Average |\<none\>|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |No|
|Nodes|**Total number of available cpu cores in a managed cluster**<p><p>Total number of available cpu cores in a managed cluster |`kube_node_status_allocatable_cpu_cores` |Count |Total, Average |\<none\>|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |No|
|Nodes|**Total amount of available memory in a managed cluster**<p><p>Total amount of available memory in a managed cluster |`kube_node_status_allocatable_memory_bytes` |Bytes |Total, Average |\<none\>|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |No|
|Nodes|**Statuses for various node conditions**<p><p>Statuses for various node conditions |`kube_node_status_condition` |Count |Total, Average |`condition`, `status`, `status2`, `node`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |No|
|Pods|**Number of pods by phase**<p><p>Number of pods by phase |`kube_pod_status_phase` |Count |Total, Average |`phase`, `namespace`, `pod`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |No|
|Pods|**Number of pods in Ready state**<p><p>Number of pods in Ready state |`kube_pod_status_ready` |Count |Total, Average |`namespace`, `pod`, `condition`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |No|
|Nodes (PREVIEW)|**CPU Usage Millicores**<p><p>Aggregated measurement of CPU utilization in millicores across the cluster |`node_cpu_usage_millicores` |MilliCores |Maximum, Average |`node`, `nodepool`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |Yes|
|Nodes (PREVIEW)|**CPU Usage Percentage**<p><p>Aggregated average CPU utilization measured in percentage across the cluster |`node_cpu_usage_percentage` |Percent |Maximum, Average |`node`, `nodepool`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |Yes|
|Nodes (PREVIEW)|**Disk Used Bytes**<p><p>Disk space used in bytes by device |`node_disk_usage_bytes` |Bytes |Maximum, Average |`node`, `nodepool`, `device`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |Yes|
|Nodes (PREVIEW)|**Disk Used Percentage**<p><p>Disk space used in percent by device |`node_disk_usage_percentage` |Percent |Maximum, Average |`node`, `nodepool`, `device`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |Yes|
|Nodes (PREVIEW)|**Memory RSS Bytes**<p><p>Container RSS memory used in bytes |`node_memory_rss_bytes` |Bytes |Maximum, Average |`node`, `nodepool`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |Yes|
|Nodes (PREVIEW)|**Memory RSS Percentage**<p><p>Container RSS memory used in percent |`node_memory_rss_percentage` |Percent |Maximum, Average |`node`, `nodepool`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |Yes|
|Nodes (PREVIEW)|**Memory Working Set Bytes**<p><p>Container working set memory used in bytes |`node_memory_working_set_bytes` |Bytes |Maximum, Average |`node`, `nodepool`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |Yes|
|Nodes (PREVIEW)|**Memory Working Set Percentage**<p><p>Container working set memory used in percent |`node_memory_working_set_percentage` |Percent |Maximum, Average |`node`, `nodepool`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |Yes|
|Nodes (PREVIEW)|**Network In Bytes**<p><p>Network received bytes |`node_network_in_bytes` |Bytes |Maximum, Average |`node`, `nodepool`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |Yes|
|Nodes (PREVIEW)|**Network Out Bytes**<p><p>Network transmitted bytes |`node_network_out_bytes` |Bytes |Maximum, Average |`node`, `nodepool`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |Yes|