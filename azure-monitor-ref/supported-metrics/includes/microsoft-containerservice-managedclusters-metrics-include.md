---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.ContainerService/managedClusters, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|API Server (PREVIEW)|**Inflight Requests**<br><br>Maximum number of currently used inflight requests on the apiserver per request kind in the last second |`apiserver_current_inflight_requests` |Count |Total, Average |`requestKind`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |No|
|Cluster Autoscaler (PREVIEW)|**Cluster Health**<br><br>Determines whether or not cluster autoscaler will take action on the cluster |`cluster_autoscaler_cluster_safe_to_autoscale` |Count |Total, Average |\<none\>|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |No|
|Cluster Autoscaler (PREVIEW)|**Scale Down Cooldown**<br><br>Determines if the scale down is in cooldown - No nodes will be removed during this timeframe |`cluster_autoscaler_scale_down_in_cooldown` |Count |Total, Average |\<none\>|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |No|
|Cluster Autoscaler (PREVIEW)|**Unneeded Nodes**<br><br>Cluster auotscaler marks those nodes as candidates for deletion and are eventually deleted |`cluster_autoscaler_unneeded_nodes_count` |Count |Total, Average |\<none\>|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |No|
|Cluster Autoscaler (PREVIEW)|**Unschedulable Pods**<br><br>Number of pods that are currently unschedulable in the cluster |`cluster_autoscaler_unschedulable_pods_count` |Count |Total, Average |\<none\>|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |No|
|Nodes|**Total number of available cpu cores in a managed cluster**<br><br>Total number of available cpu cores in a managed cluster |`kube_node_status_allocatable_cpu_cores` |Count |Total, Average |\<none\>|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |No|
|Nodes|**Total amount of available memory in a managed cluster**<br><br>Total amount of available memory in a managed cluster |`kube_node_status_allocatable_memory_bytes` |Bytes |Total, Average |\<none\>|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |No|
|Nodes|**Statuses for various node conditions**<br><br>Statuses for various node conditions |`kube_node_status_condition` |Count |Total, Average |`condition`, `status`, `status2`, `node`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |No|
|Pods|**Number of pods by phase**<br><br>Number of pods by phase |`kube_pod_status_phase` |Count |Total, Average |`phase`, `namespace`, `pod`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |No|
|Pods|**Number of pods in Ready state**<br><br>Number of pods in Ready state |`kube_pod_status_ready` |Count |Total, Average |`namespace`, `pod`, `condition`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |No|
|Nodes (PREVIEW)|**CPU Usage Millicores**<br><br>Aggregated measurement of CPU utilization in millicores across the cluster |`node_cpu_usage_millicores` |MilliCores |Maximum, Average |`node`, `nodepool`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |Yes|
|Nodes (PREVIEW)|**CPU Usage Percentage**<br><br>Aggregated average CPU utilization measured in percentage across the cluster |`node_cpu_usage_percentage` |Percent |Maximum, Average |`node`, `nodepool`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |Yes|
|Nodes (PREVIEW)|**Disk Used Bytes**<br><br>Disk space used in bytes by device |`node_disk_usage_bytes` |Bytes |Maximum, Average |`node`, `nodepool`, `device`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |Yes|
|Nodes (PREVIEW)|**Disk Used Percentage**<br><br>Disk space used in percent by device |`node_disk_usage_percentage` |Percent |Maximum, Average |`node`, `nodepool`, `device`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |Yes|
|Nodes (PREVIEW)|**Memory RSS Bytes**<br><br>Container RSS memory used in bytes |`node_memory_rss_bytes` |Bytes |Maximum, Average |`node`, `nodepool`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |Yes|
|Nodes (PREVIEW)|**Memory RSS Percentage**<br><br>Container RSS memory used in percent |`node_memory_rss_percentage` |Percent |Maximum, Average |`node`, `nodepool`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |Yes|
|Nodes (PREVIEW)|**Memory Working Set Bytes**<br><br>Container working set memory used in bytes |`node_memory_working_set_bytes` |Bytes |Maximum, Average |`node`, `nodepool`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |Yes|
|Nodes (PREVIEW)|**Memory Working Set Percentage**<br><br>Container working set memory used in percent |`node_memory_working_set_percentage` |Percent |Maximum, Average |`node`, `nodepool`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |Yes|
|Nodes (PREVIEW)|**Network In Bytes**<br><br>Network received bytes |`node_network_in_bytes` |Bytes |Maximum, Average |`node`, `nodepool`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |Yes|
|Nodes (PREVIEW)|**Network Out Bytes**<br><br>Network transmitted bytes |`node_network_out_bytes` |Bytes |Maximum, Average |`node`, `nodepool`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H |Yes|