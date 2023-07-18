---
title: Supported metrics - Microsoft.DataShare/accounts
description: Reference for Microsoft.DataShare/accounts metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.DataShare/accounts  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.DataShare/accounts resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Received Share Failed Snapshots<p><p>Number of received share failed snapshots in the account |`FailedShareSubscriptionSynchronizations` |Count |Count |No Dimensions |Yes|
|Sent Share Failed Snapshots<p><p>Number of sent share failed snapshots in the account |`FailedShareSynchronizations` |Count |Count |No Dimensions |Yes|
|Sent Shares<p><p>Number of sent shares in the account |`ShareCount` |Count |Maximum |ShareName |Yes|
|Received Shares<p><p>Number of received shares in the account |`ShareSubscriptionCount` |Count |Maximum |ShareSubscriptionName |Yes|
|Received Share Succeeded Snapshots<p><p>Number of received share succeeded snapshots in the account |`SucceededShareSubscriptionSynchronizations` |Count |Count |No Dimensions |Yes|
|Sent Share Succeeded Snapshots<p><p>Number of sent share succeeded snapshots in the account |`SucceededShareSynchronizations` |Count |Count |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->