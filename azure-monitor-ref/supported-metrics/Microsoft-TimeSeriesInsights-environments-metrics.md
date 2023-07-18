---
title: Supported metrics - Microsoft.TimeSeriesInsights/environments
description: Reference for Microsoft.TimeSeriesInsights/environments metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.TimeSeriesInsights/environments  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.TimeSeriesInsights/environments resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Ingress Received Bytes<p><p>Count of bytes read from all event sources |`IngressReceivedBytes` |Bytes |Total |No Dimensions |Yes|
|Ingress Received Invalid Messages<p><p>Count of invalid messages read from all Event hub or IoT hub event sources |`IngressReceivedInvalidMessages` |Count |Total |No Dimensions |Yes|
|Ingress Received Messages<p><p>Count of messages read from all Event hub or IoT hub event sources |`IngressReceivedMessages` |Count |Total |No Dimensions |Yes|
|Ingress Received Messages Count Lag<p><p>Difference between the sequence number of last enqueued message in the event source partition and sequence number of messages being processed in Ingress |`IngressReceivedMessagesCountLag` |Count |Average |No Dimensions |Yes|
|Ingress Received Messages Time Lag<p><p>Difference between the time that the message is enqueued in the event source and the time it is processed in Ingress |`IngressReceivedMessagesTimeLag` |Seconds |Maximum |No Dimensions |Yes|
|Ingress Stored Bytes<p><p>Total size of events successfully processed and available for query |`IngressStoredBytes` |Bytes |Total |No Dimensions |Yes|
|Ingress Stored Events<p><p>Count of flattened events successfully processed and available for query |`IngressStoredEvents` |Count |Total |No Dimensions |Yes|
|Warm Storage Max Properties<p><p>Maximum number of properties used allowed by the environment for S1/S2 SKU and maximum number of properties allowed by Warm Store for PAYG SKU |`WarmStorageMaxProperties` |Count |Maximum |No Dimensions |Yes|
|Warm Storage Used Properties <p><p>Number of properties used by the environment for S1/S2 SKU and number of properties used by Warm Store for PAYG SKU |`WarmStorageUsedProperties` |Count |Maximum |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->