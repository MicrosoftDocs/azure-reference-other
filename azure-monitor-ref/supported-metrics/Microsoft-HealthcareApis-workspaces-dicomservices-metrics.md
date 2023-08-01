---
title: Supported metrics - Microsoft.HealthcareApis/workspaces/dicomservices
description: Reference for Microsoft.HealthcareApis/workspaces/dicomservices metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 08/01/2023
---
# Supported metrics for Microsoft.HealthcareApis/workspaces/dicomservices  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.HealthcareApis/workspaces/dicomservices resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Number of DICOM files processed by import<p><p>The total number of DICOM files processed by an import. |`ImportsProcessed` |Count |Sum |Status, ResourceName |Yes|


<!--Gen Date:  Tue Aug 01 2023 10:39:24 GMT+0300 (Israel Daylight Time)-->