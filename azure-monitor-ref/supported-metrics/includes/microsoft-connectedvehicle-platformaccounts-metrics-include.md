---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.ConnectedVehicle/platformAccounts, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Claims request execution time**<br><br>The average execution time of requests to the customer claims provider endpoint in milliseconds. |`ClaimsProviderRequestLatency` |Milliseconds |Average |`IsSuccessful`, `FailureCategory`|PT1M |Yes|
|**Claims provider requests**<br><br>Number of requests to claims provider |`ClaimsProviderRequests` |Count |Total |`IsSuccessful`, `FailureCategory`|PT1M |Yes|
|**Vehicle connection service request execution time**<br><br>Vehicle conneciton request execution time average in milliseconds |`ConnectionServiceRequestRuntime` |Milliseconds |Average |`IsSuccessful`, `FailureCategory`|PT1M |Yes|
|**Vehicle connection service requests**<br><br>Total number of vehicle connection requests |`ConnectionServiceRequests` |Count |Total |`IsSuccessful`, `FailureCategory`|PT1M |Yes|
|**Data pipeline message count**<br><br>The total number of messages sent to the MCVP data pipeline for storage. |`DataPipelineMessageCount` |Count |Total |`IsSuccessful`, `FailureCategory`|PT1M |Yes|
|**Extension invocation count**<br><br>Total number of times an extension was called. |`ExtensionInvocationCount` |Count |Total |`ExtensionName`, `IsSuccessful`, `FailureCategory`|PT1M |Yes|
|**Extension invocation execution time**<br><br>Average execution time spent inside an extension in milliseconds. |`ExtensionInvocationRuntime` |Milliseconds |Average |`ExtensionName`, `IsSuccessful`, `FailureCategory`|PT1M |Yes|
|**Messages received count**<br><br>The total number of vehicle-sourced publishes. |`MessagesInCount` |Count |Total |`IsSuccessful`, `FailureCategory`|PT1M |Yes|
|**Messages sent count**<br><br>The total number of cloud-sourced publishes. |`MessagesOutCount` |Count |Total |`IsSuccessful`, `FailureCategory`|PT1M |Yes|
|**Vehicle provision execution time**<br><br>The average execution time of vehicle provision requests in milliseconds |`ProvisionerServiceRequestRuntime` |Milliseconds |Average |`IsSuccessful`, `FailureCategory`|PT1M |Yes|
|**Vehicle provision service requests**<br><br>Total number of vehicle provision requests |`ProvisionerServiceRequests` |Count |Total |`IsSuccessful`, `FailureCategory`|PT1M |Yes|
|**State store read execution time**<br><br>State store read request execution time average in milliseconds. |`StateStoreReadRequestLatency` |Milliseconds |Average |`ExtensionName`, `IsSuccessful`, `FailureCategory`|PT1M |Yes|
|**State store read requests**<br><br>Number of read requests to state store |`StateStoreReadRequests` |Count |Total |`ExtensionName`, `IsSuccessful`, `FailureCategory`|PT1M |Yes|
|**State store write execution time**<br><br>State store write request execution time average in milliseconds. |`StateStoreWriteRequestLatency` |Milliseconds |Average |`ExtensionName`, `IsSuccessful`, `FailureCategory`|PT1M |Yes|
|**State store write requests**<br><br>Number of write requests to state store |`StateStoreWriteRequests` |Count |Total |`ExtensionName`, `IsSuccessful`, `FailureCategory`|PT1M |Yes|