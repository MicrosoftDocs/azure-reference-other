---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.ClassicStorage/storageAccounts/tableServices, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Transaction|**Availability**<p><p>The percentage of availability for the storage service or the specified API operation. Availability is calculated by taking the TotalBillableRequests value and dividing it by the number of applicable requests, including those that produced unexpected errors. All unexpected errors result in reduced availability for the storage service or the specified API operation. |`Availability` |Percent |Average, Minimum, Maximum |`GeoType`, `ApiName`, `Authentication`|PT1M |Yes|
|Transaction|**Egress**<p><p>The amount of egress data, in bytes. This number includes egress from an external client into Azure Storage as well as egress within Azure. As a result, this number does not reflect billable egress. |`Egress` |Bytes |Total, Average, Minimum, Maximum |`GeoType`, `ApiName`, `Authentication`|PT1M |Yes|
|Transaction|**Ingress**<p><p>The amount of ingress data, in bytes. This number includes ingress from an external client into Azure Storage as well as ingress within Azure. |`Ingress` |Bytes |Total, Average, Minimum, Maximum |`GeoType`, `ApiName`, `Authentication`|PT1M |Yes|
|Transaction|**Success E2E Latency**<p><p>The end-to-end latency of successful requests made to a storage service or the specified API operation, in milliseconds. This value includes the required processing time within Azure Storage to read the request, send the response, and receive acknowledgment of the response. |`SuccessE2ELatency` |Milliseconds |Average, Minimum, Maximum |`GeoType`, `ApiName`, `Authentication`|PT1M |Yes|
|Transaction|**Success Server Latency**<p><p>The latency used by Azure Storage to process a successful request, in milliseconds. This value does not include the network latency specified in SuccessE2ELatency. |`SuccessServerLatency` |Milliseconds |Average, Minimum, Maximum |`GeoType`, `ApiName`, `Authentication`|PT1M |Yes|
|Capacity|**Table Capacity**<p><p>The amount of storage used by the storage account's Table service in bytes. |`TableCapacity` |Bytes |Average |\<none\>|PT1H |No|
|Capacity|**Table Count**<p><p>The number of table in the storage account's Table service. |`TableCount` |Count |Average |\<none\>|PT1H |No|
|Capacity|**Table Entity Count**<p><p>The number of table entities in the storage account's Table service. |`TableEntityCount` |Count |Average |\<none\>|PT1H |No|
|Transaction|**Transactions**<p><p>The number of requests made to a storage service or the specified API operation. This number includes successful and failed requests, as well as requests which produced errors. Use ResponseType dimension for the number of different type of response. |`Transactions` |Count |Total |`ResponseType`, `GeoType`, `ApiName`, `Authentication`|PT1M |Yes|