---
title: Supported metrics - Microsoft.ConnectedVehicle/platformAccounts
description: Reference for Microsoft.ConnectedVehicle/platformAccounts metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.ConnectedVehicle/platformAccounts  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.ConnectedVehicle/platformAccounts resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Claims request execution time<p><p>The average execution time of requests to the customer claims provider endpoint in milliseconds. |`ClaimsProviderRequestLatency` |Milliseconds |Average |IsSuccessful, FailureCategory |Yes|
|Claims provider requests<p><p>Number of requests to claims provider |`ClaimsProviderRequests` |Count |Total |IsSuccessful, FailureCategory |Yes|
|Vehicle connection service request execution time<p><p>Vehicle conneciton request execution time average in milliseconds |`ConnectionServiceRequestRuntime` |Milliseconds |Average |IsSuccessful, FailureCategory |Yes|
|Vehicle connection service requests<p><p>Total number of vehicle connection requests |`ConnectionServiceRequests` |Count |Total |IsSuccessful, FailureCategory |Yes|
|Data pipeline message count<p><p>The total number of messages sent to the MCVP data pipeline for storage. |`DataPipelineMessageCount` |Count |Total |IsSuccessful, FailureCategory |Yes|
|Extension invocation count<p><p>Total number of times an extension was called. |`ExtensionInvocationCount` |Count |Total |ExtensionName, IsSuccessful, FailureCategory |Yes|
|Extension invocation execution time<p><p>Average execution time spent inside an extension in milliseconds. |`ExtensionInvocationRuntime` |Milliseconds |Average |ExtensionName, IsSuccessful, FailureCategory |Yes|
|Messages received count<p><p>The total number of vehicle-sourced publishes. |`MessagesInCount` |Count |Total |IsSuccessful, FailureCategory |Yes|
|Messages sent count<p><p>The total number of cloud-sourced publishes. |`MessagesOutCount` |Count |Total |IsSuccessful, FailureCategory |Yes|
|Vehicle provision execution time<p><p>The average execution time of vehicle provision requests in milliseconds |`ProvisionerServiceRequestRuntime` |Milliseconds |Average |IsSuccessful, FailureCategory |Yes|
|Vehicle provision service requests<p><p>Total number of vehicle provision requests |`ProvisionerServiceRequests` |Count |Total |IsSuccessful, FailureCategory |Yes|
|State store read execution time<p><p>State store read request execution time average in milliseconds. |`StateStoreReadRequestLatency` |Milliseconds |Average |ExtensionName, IsSuccessful, FailureCategory |Yes|
|State store read requests<p><p>Number of read requests to state store |`StateStoreReadRequests` |Count |Total |ExtensionName, IsSuccessful, FailureCategory |Yes|
|State store write execution time<p><p>State store write request execution time average in milliseconds. |`StateStoreWriteRequestLatency` |Milliseconds |Average |ExtensionName, IsSuccessful, FailureCategory |Yes|
|State store write requests<p><p>Number of write requests to state store |`StateStoreWriteRequests` |Count |Total |ExtensionName, IsSuccessful, FailureCategory |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->