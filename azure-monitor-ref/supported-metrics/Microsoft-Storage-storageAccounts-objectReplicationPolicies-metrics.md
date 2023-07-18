---
title: Supported metrics - Microsoft.Storage/storageAccounts/objectReplicationPolicies
description: Reference for Microsoft.Storage/storageAccounts/objectReplicationPolicies metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Storage/storageAccounts/objectReplicationPolicies  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Storage/storageAccounts/objectReplicationPolicies resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Pending Bytes for Replication (PREVIEW)<p><p>The size in bytes of the blob object pending for replication, please note, this metric is in preview and is subject to change before becoming generally available |`PendingBytesForReplication` |Bytes |Average |TimeBucket |No|
|Pending Operations for Replication (PREVIEW)<p><p>The count of pending operations for replication, please note, this metric is in preview and is subject to change before becoming generally available |`PendingOperationsForReplication` |Count |Average |TimeBucket |No|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->