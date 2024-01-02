---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Automation/automationAccounts, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Hybrid Worker Ping**<p><p>The number of pings from the hybrid worker |`HybridWorkerPing` |Count |Total, Average, Maximum, Minimum, Count |`HybridWorkerGroup`, `HybridWorker`, `HybridWorkerVersion`|PT1M |Yes|
|**Total Jobs**<p><p>The total number of jobs |`TotalJob` |Count |Total, Average, Maximum, Minimum, Count |`Runbook`, `Status`|PT1M |Yes|
|**Total Update Deployment Machine Runs**<p><p>Total software update deployment machine runs in a software update deployment run |`TotalUpdateDeploymentMachineRuns` |Count |Total, Average, Maximum, Minimum, Count |`Status`, `TargetComputer`, `SoftwareUpdateConfigurationName`, `SoftwareUpdateConfigurationRunId`|PT1M |Yes|
|**Total Update Deployment Runs**<p><p>Total software update deployment runs |`TotalUpdateDeploymentRuns` |Count |Total, Average, Maximum, Minimum, Count |`Status`, `SoftwareUpdateConfigurationName`|PT1M |Yes|