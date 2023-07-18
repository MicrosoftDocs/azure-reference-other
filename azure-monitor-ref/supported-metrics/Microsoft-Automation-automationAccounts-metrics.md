---
title: Supported metrics - Microsoft.Automation/automationAccounts
description: Reference for Microsoft.Automation/automationAccounts metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Automation/automationAccounts  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Automation/automationAccounts resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Hybrid Worker Ping<p><p>The number of pings from the hybrid worker |`HybridWorkerPing` |Count |Count |HybridWorkerGroup, HybridWorker, HybridWorkerVersion |Yes|
|Total Jobs<p><p>The total number of jobs |`TotalJob` |Count |Total |Runbook, Status |Yes|
|Total Update Deployment Machine Runs<p><p>Total software update deployment machine runs in a software update deployment run |`TotalUpdateDeploymentMachineRuns` |Count |Total |Status, TargetComputer, SoftwareUpdateConfigurationName, SoftwareUpdateConfigurationRunId |Yes|
|Total Update Deployment Runs<p><p>Total software update deployment runs |`TotalUpdateDeploymentRuns` |Count |Total |Status, SoftwareUpdateConfigurationName |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->