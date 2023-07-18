---
title: Supported metrics - Microsoft.Orbital/contactProfiles
description: Reference for Microsoft.Orbital/contactProfiles metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Orbital/contactProfiles  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Orbital/contactProfiles resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Contact Failure Count<p><p>Denotes the number of failed Contacts for a specific Contact Profile |`ContactFailure` |Count |Count |No Dimensions |Yes|
|Contact Success Count<p><p>Denotes the number of successful Contacts for a specific Contact Profile |`ContactSuccess` |Count |Count |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->