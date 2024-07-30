---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.ClassicStorage/storageAccounts/fileServices, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Transaction|**Availability**<br><br>The percentage of availability for the storage service or the specified API operation. Availability is calculated by taking the TotalBillableRequests value and dividing it by the number of applicable requests, including those that produced unexpected errors. All unexpected errors result in reduced availability for the storage service or the specified API operation. |`Availability` |Percent |Average, Minimum, Maximum |`GeoType`, `ApiName`, `Authentication`, `FileShare`|PT1M |Yes|
|Transaction|**Egress**<br><br>The amount of egress data, in bytes. This number includes egress from an external client into Azure Storage as well as egress within Azure. As a result, this number does not reflect billable egress. |`Egress` |Bytes |Total, Average, Minimum, Maximum |`GeoType`, `ApiName`, `Authentication`, `FileShare`|PT1M |Yes|
|Capacity|**File Capacity**<br><br>The amount of storage used by the storage account's File service in bytes. |`FileCapacity` |Bytes |Average |`FileShare`|PT1H |No|
|Capacity|**File Count**<br><br>The number of file in the storage account's File service. |`FileCount` |Count |Average |`FileShare`|PT1H |No|
|Capacity|**File Share Count**<br><br>The number of file shares in the storage account's File service. |`FileShareCount` |Count |Average |\<none\>|PT1H |No|
|Capacity|**File share quota size**<br><br>The upper limit on the amount of storage that can be used by Azure Files Service in bytes. |`FileShareQuota` |Bytes |Average |`FileShare`|PT1H |No|
|Capacity|**File Share Snapshot Count**<br><br>The number of snapshots present on the share in storage account's Files Service. |`FileShareSnapshotCount` |Count |Average |`FileShare`|PT1H |No|
|Capacity|**File Share Snapshot Size**<br><br>The amount of storage used by the snapshots in storage account's File service in bytes. |`FileShareSnapshotSize` |Bytes |Average |`FileShare`|PT1H |No|
|Transaction|**Ingress**<br><br>The amount of ingress data, in bytes. This number includes ingress from an external client into Azure Storage as well as ingress within Azure. |`Ingress` |Bytes |Total, Average, Minimum, Maximum |`GeoType`, `ApiName`, `Authentication`, `FileShare`|PT1M |Yes|
|Transaction|**Success E2E Latency**<br><br>The end-to-end latency of successful requests made to a storage service or the specified API operation, in milliseconds. This value includes the required processing time within Azure Storage to read the request, send the response, and receive acknowledgment of the response. |`SuccessE2ELatency` |Milliseconds |Average, Minimum, Maximum |`GeoType`, `ApiName`, `Authentication`, `FileShare`|PT1M |Yes|
|Transaction|**Success Server Latency**<br><br>The latency used by Azure Storage to process a successful request, in milliseconds. This value does not include the network latency specified in SuccessE2ELatency. |`SuccessServerLatency` |Milliseconds |Average, Minimum, Maximum |`GeoType`, `ApiName`, `Authentication`, `FileShare`|PT1M |Yes|
|Transaction|**Transactions**<br><br>The number of requests made to a storage service or the specified API operation. This number includes successful and failed requests, as well as requests which produced errors. Use ResponseType dimension for the number of different type of response. |`Transactions` |Count |Total |`ResponseType`, `GeoType`, `ApiName`, `Authentication`, `FileShare`|PT1M |Yes|