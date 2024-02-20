---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Logic/IntegrationServiceEnvironments, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Action Latency**<br><br>Latency of completed workflow actions. |`ActionLatency` |Seconds |Average |\<none\>|PT1M |Yes|
|**Actions Completed**<br><br>Number of workflow actions completed. |`ActionsCompleted` |Count |Total |\<none\>|PT1M |Yes|
|**Actions Failed**<br><br>Number of workflow actions failed. |`ActionsFailed` |Count |Total |\<none\>|PT1M |Yes|
|**Actions Skipped**<br><br>Number of workflow actions skipped. |`ActionsSkipped` |Count |Total |\<none\>|PT1M |Yes|
|**Actions Started**<br><br>Number of workflow actions started. |`ActionsStarted` |Count |Total |\<none\>|PT1M |Yes|
|**Actions Succeeded**<br><br>Number of workflow actions succeeded. |`ActionsSucceeded` |Count |Total |\<none\>|PT1M |Yes|
|**Action Success Latency**<br><br>Latency of succeeded workflow actions. |`ActionSuccessLatency` |Seconds |Average |\<none\>|PT1M |Yes|
|**Connector Memory Usage for Integration Service Environment**<br><br>Connector memory usage for integration service environment. |`IntegrationServiceEnvironmentConnectorMemoryUsage` |Percent |Average |\<none\>|PT1M |Yes|
|**Connector Processor Usage for Integration Service Environment**<br><br>Connector processor usage for integration service environment. |`IntegrationServiceEnvironmentConnectorProcessorUsage` |Percent |Average |\<none\>|PT1M |Yes|
|**Workflow Memory Usage for Integration Service Environment**<br><br>Workflow memory usage for integration service environment. |`IntegrationServiceEnvironmentWorkflowMemoryUsage` |Percent |Average |\<none\>|PT1M |Yes|
|**Workflow Processor Usage for Integration Service Environment**<br><br>Workflow processor usage for integration service environment. |`IntegrationServiceEnvironmentWorkflowProcessorUsage` |Percent |Average |\<none\>|PT1M |Yes|
|**Run Latency**<br><br>Latency of completed workflow runs. |`RunLatency` |Seconds |Average |\<none\>|PT1M |Yes|
|**Runs Cancelled**<br><br>Number of workflow runs cancelled. |`RunsCancelled` |Count |Total |\<none\>|PT1M |Yes|
|**Runs Completed**<br><br>Number of workflow runs completed. |`RunsCompleted` |Count |Total |\<none\>|PT1M |Yes|
|**Runs Failed**<br><br>Number of workflow runs failed. |`RunsFailed` |Count |Total |\<none\>|PT1M |Yes|
|**Runs Started**<br><br>Number of workflow runs started. |`RunsStarted` |Count |Total |\<none\>|PT1M |Yes|
|**Runs Succeeded**<br><br>Number of workflow runs succeeded. |`RunsSucceeded` |Count |Total |\<none\>|PT1M |Yes|
|**Run Success Latency**<br><br>Latency of succeeded workflow runs. |`RunSuccessLatency` |Seconds |Average |\<none\>|PT1M |Yes|
|**Trigger Fire Latency**<br><br>Latency of fired workflow triggers. |`TriggerFireLatency` |Seconds |Average |\<none\>|PT1M |Yes|
|**Trigger Latency**<br><br>Latency of completed workflow triggers. |`TriggerLatency` |Seconds |Average |\<none\>|PT1M |Yes|
|**Triggers Completed**<br><br>Number of workflow triggers completed. |`TriggersCompleted` |Count |Total |\<none\>|PT1M |Yes|
|**Triggers Failed**<br><br>Number of workflow triggers failed. |`TriggersFailed` |Count |Total |\<none\>|PT1M |Yes|
|**Triggers Fired**<br><br>Number of workflow triggers fired. |`TriggersFired` |Count |Total |\<none\>|PT1M |Yes|
|**Triggers Skipped**<br><br>Number of workflow triggers skipped. |`TriggersSkipped` |Count |Total |\<none\>|PT1M |Yes|
|**Triggers Started**<br><br>Number of workflow triggers started. |`TriggersStarted` |Count |Total |\<none\>|PT1M |Yes|
|**Triggers Succeeded**<br><br>Number of workflow triggers succeeded. |`TriggersSucceeded` |Count |Total |\<none\>|PT1M |Yes|
|**Trigger Success Latency**<br><br>Latency of succeeded workflow triggers. |`TriggerSuccessLatency` |Seconds |Average |\<none\>|PT1M |Yes|