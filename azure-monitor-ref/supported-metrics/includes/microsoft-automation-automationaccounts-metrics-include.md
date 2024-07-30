---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.Automation/automationAccounts, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Hybrid Worker Ping**<br><br>The number of pings from the hybrid worker |`HybridWorkerPing` |Count |Total, Average, Maximum, Minimum, Count |`HybridWorkerGroup`, `HybridWorker`, `HybridWorkerVersion`|PT1M |Yes|
|**Total Jobs**<br><br>The total number of jobs |`TotalJob` |Count |Total, Average, Maximum, Minimum, Count |`Runbook`, `Status`|PT1M |Yes|
|**Total Update Deployment Machine Runs**<br><br>Total software update deployment machine runs in a software update deployment run |`TotalUpdateDeploymentMachineRuns` |Count |Total, Average, Maximum, Minimum, Count |`Status`, `TargetComputer`, `SoftwareUpdateConfigurationName`, `SoftwareUpdateConfigurationRunId`|PT1M |Yes|
|**Total Update Deployment Runs**<br><br>Total software update deployment runs |`TotalUpdateDeploymentRuns` |Count |Total, Average, Maximum, Minimum, Count |`Status`, `SoftwareUpdateConfigurationName`|PT1M |Yes|