---
title: Supported metrics - Microsoft.ClassicStorage/storageAccounts/fileServices
description: Reference for Microsoft.ClassicStorage/storageAccounts/fileServices metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.ClassicStorage/storageAccounts/fileServices  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.ClassicStorage/storageAccounts/fileServices resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Availability<p><p>The percentage of availability for the storage service or the specified API operation. Availability is calculated by taking the TotalBillableRequests value and dividing it by the number of applicable requests, including those that produced unexpected errors. All unexpected errors result in reduced availability for the storage service or the specified API operation. |`Availability` |Percent |Average |GeoType, ApiName, Authentication, FileShare |Yes|
|Egress<p><p>The amount of egress data, in bytes. This number includes egress from an external client into Azure Storage as well as egress within Azure. As a result, this number does not reflect billable egress. |`Egress` |Bytes |Total |GeoType, ApiName, Authentication, FileShare |Yes|
|File Capacity<p><p>The amount of storage used by the storage account's File service in bytes. |`FileCapacity` |Bytes |Average |FileShare |No|
|File Count<p><p>The number of file in the storage account's File service. |`FileCount` |Count |Average |FileShare |No|
|File Share Count<p><p>The number of file shares in the storage account's File service. |`FileShareCount` |Count |Average |No Dimensions |No|
|File share quota size<p><p>The upper limit on the amount of storage that can be used by Azure Files Service in bytes. |`FileShareQuota` |Bytes |Average |FileShare |No|
|File Share Snapshot Count<p><p>The number of snapshots present on the share in storage account's Files Service. |`FileShareSnapshotCount` |Count |Average |FileShare |No|
|File Share Snapshot Size<p><p>The amount of storage used by the snapshots in storage account's File service in bytes. |`FileShareSnapshotSize` |Bytes |Average |FileShare |No|
|Ingress<p><p>The amount of ingress data, in bytes. This number includes ingress from an external client into Azure Storage as well as ingress within Azure. |`Ingress` |Bytes |Total |GeoType, ApiName, Authentication, FileShare |Yes|
|Success E2E Latency<p><p>The end-to-end latency of successful requests made to a storage service or the specified API operation, in milliseconds. This value includes the required processing time within Azure Storage to read the request, send the response, and receive acknowledgment of the response. |`SuccessE2ELatency` |Milliseconds |Average |GeoType, ApiName, Authentication, FileShare |Yes|
|Success Server Latency<p><p>The latency used by Azure Storage to process a successful request, in milliseconds. This value does not include the network latency specified in SuccessE2ELatency. |`SuccessServerLatency` |Milliseconds |Average |GeoType, ApiName, Authentication, FileShare |Yes|
|Transactions<p><p>The number of requests made to a storage service or the specified API operation. This number includes successful and failed requests, as well as requests which produced errors. Use ResponseType dimension for the number of different type of response. |`Transactions` |Count |Total |ResponseType, GeoType, ApiName, Authentication, FileShare |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->