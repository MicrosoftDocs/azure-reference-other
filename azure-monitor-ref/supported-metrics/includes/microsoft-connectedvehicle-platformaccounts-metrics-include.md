---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.ConnectedVehicle/platformAccounts, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Claims request execution time**<p><p>The average execution time of requests to the customer claims provider endpoint in milliseconds. |`ClaimsProviderRequestLatency` |Milliseconds |Average |`IsSuccessful`, `FailureCategory`|PT1M |Yes|
|**Claims provider requests**<p><p>Number of requests to claims provider |`ClaimsProviderRequests` |Count |Total |`IsSuccessful`, `FailureCategory`|PT1M |Yes|
|**Vehicle connection service request execution time**<p><p>Vehicle conneciton request execution time average in milliseconds |`ConnectionServiceRequestRuntime` |Milliseconds |Average |`IsSuccessful`, `FailureCategory`|PT1M |Yes|
|**Vehicle connection service requests**<p><p>Total number of vehicle connection requests |`ConnectionServiceRequests` |Count |Total |`IsSuccessful`, `FailureCategory`|PT1M |Yes|
|**Data pipeline message count**<p><p>The total number of messages sent to the MCVP data pipeline for storage. |`DataPipelineMessageCount` |Count |Total |`IsSuccessful`, `FailureCategory`|PT1M |Yes|
|**Extension invocation count**<p><p>Total number of times an extension was called. |`ExtensionInvocationCount` |Count |Total |`ExtensionName`, `IsSuccessful`, `FailureCategory`|PT1M |Yes|
|**Extension invocation execution time**<p><p>Average execution time spent inside an extension in milliseconds. |`ExtensionInvocationRuntime` |Milliseconds |Average |`ExtensionName`, `IsSuccessful`, `FailureCategory`|PT1M |Yes|
|**Messages received count**<p><p>The total number of vehicle-sourced publishes. |`MessagesInCount` |Count |Total |`IsSuccessful`, `FailureCategory`|PT1M |Yes|
|**Messages sent count**<p><p>The total number of cloud-sourced publishes. |`MessagesOutCount` |Count |Total |`IsSuccessful`, `FailureCategory`|PT1M |Yes|
|**Vehicle provision execution time**<p><p>The average execution time of vehicle provision requests in milliseconds |`ProvisionerServiceRequestRuntime` |Milliseconds |Average |`IsSuccessful`, `FailureCategory`|PT1M |Yes|
|**Vehicle provision service requests**<p><p>Total number of vehicle provision requests |`ProvisionerServiceRequests` |Count |Total |`IsSuccessful`, `FailureCategory`|PT1M |Yes|
|**State store read execution time**<p><p>State store read request execution time average in milliseconds. |`StateStoreReadRequestLatency` |Milliseconds |Average |`ExtensionName`, `IsSuccessful`, `FailureCategory`|PT1M |Yes|
|**State store read requests**<p><p>Number of read requests to state store |`StateStoreReadRequests` |Count |Total |`ExtensionName`, `IsSuccessful`, `FailureCategory`|PT1M |Yes|
|**State store write execution time**<p><p>State store write request execution time average in milliseconds. |`StateStoreWriteRequestLatency` |Milliseconds |Average |`ExtensionName`, `IsSuccessful`, `FailureCategory`|PT1M |Yes|
|**State store write requests**<p><p>Number of write requests to state store |`StateStoreWriteRequests` |Count |Total |`ExtensionName`, `IsSuccessful`, `FailureCategory`|PT1M |Yes|