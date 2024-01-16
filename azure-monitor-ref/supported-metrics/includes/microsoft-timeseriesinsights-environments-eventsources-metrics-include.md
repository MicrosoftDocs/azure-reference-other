---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.TimeSeriesInsights/environments/eventsources, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Ingress Received Bytes**<p><p>Count of bytes read from the event source |`IngressReceivedBytes` |Bytes |Total |\<none\>|PT1M |Yes|
|**Ingress Received Invalid Messages**<p><p>Count of invalid messages read from the event source |`IngressReceivedInvalidMessages` |Count |Total |\<none\>|PT1M |Yes|
|**Ingress Received Messages**<p><p>Count of messages read from the event source |`IngressReceivedMessages` |Count |Total |\<none\>|PT1M |Yes|
|**Ingress Received Messages Count Lag**<p><p>Difference between the sequence number of last enqueued message in the event source partition and sequence number of messages being processed in Ingress |`IngressReceivedMessagesCountLag` |Count |Average |\<none\>|PT1M |Yes|
|**Ingress Received Messages Time Lag**<p><p>Difference between the time that the message is enqueued in the event source and the time it is processed in Ingress |`IngressReceivedMessagesTimeLag` |Seconds |Maximum |\<none\>|PT1M |Yes|
|**Ingress Stored Bytes**<p><p>Total size of events successfully processed and available for query |`IngressStoredBytes` |Bytes |Total |\<none\>|PT1M |Yes|
|**Ingress Stored Events**<p><p>Count of flattened events successfully processed and available for query |`IngressStoredEvents` |Count |Total |\<none\>|PT1M |Yes|
|**Warm Storage Max Properties**<p><p>Maximum number of properties used allowed by the environment for S1/S2 SKU and maximum number of properties allowed by Warm Store for PAYG SKU |`WarmStorageMaxProperties` |Count |Maximum |\<none\>|PT1M |Yes|
|**Warm Storage Used Properties**<p><p>Number of properties used by the environment for S1/S2 SKU and number of properties used by Warm Store for PAYG SKU |`WarmStorageUsedProperties` |Count |Maximum |\<none\>|PT1M |Yes|