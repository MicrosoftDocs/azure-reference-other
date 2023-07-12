---
title: Supported metrics - Microsoft.KeyVault/vaults
description: Reference for Microsoft.KeyVault/vaults metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.KeyVault/vaults  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.KeyVault/vaults resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Overall Vault Availability<p><p>Vault requests availability |`Availability` |Percent |Average |ActivityType, ActivityName, StatusCode, StatusCodeClass |Yes|
|Overall Vault Saturation<p><p>Vault capacity used |`SaturationShoebox` |Percent |Average |ActivityType, ActivityName, TransactionType |No|
|Total Service Api Hits<p><p>Number of total service api hits |`ServiceApiHit` |Count |Count |ActivityType, ActivityName |Yes|
|Overall Service Api Latency<p><p>Overall latency of service api requests |`ServiceApiLatency` |MilliSeconds |Average |ActivityType, ActivityName, StatusCode, StatusCodeClass |Yes|
|Total Service Api Results<p><p>Number of total service api results |`ServiceApiResult` |Count |Count |ActivityType, ActivityName, StatusCode, StatusCodeClass |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->