---
title: Supported metrics - Microsoft.DataCollaboration/workspaces
description: Reference for Microsoft.DataCollaboration/workspaces metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.DataCollaboration/workspaces  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.DataCollaboration/workspaces resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Created Computations<p><p>Number of created computations |`ComputationCount` |Count |Maximum |ComputationName |Yes|
|Created Data Assets<p><p>Number of created data assets |`DataAssetCount` |Count |Maximum |DataAssetName |Yes|
|Created Pipelines<p><p>Number of created pipelines |`PipelineCount` |Count |Maximum |PipelineName |Yes|
|Created Pipelines<p><p>Number of created pipelines |`PipelineCount` |Count |Maximum |PipelineName |Yes|
|Created Proposals<p><p>Number of created proposals |`ProposalCount` |Count |Maximum |ProposalName |Yes|
|Created Scripts<p><p>Number of created scripts |`ScriptCount` |Count |Maximum |ScriptName |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->