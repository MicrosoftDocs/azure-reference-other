---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.Logic/Workflows, naam

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
|**Action Throttled Events**<br><br>Number of workflow action throttled events.. |`ActionThrottledEvents` |Count |Total |\<none\>|PT1M |Yes|
|**Billable Action Executions**<br><br>Number of workflow action executions getting billed. |`BillableActionExecutions` |Count |Total |\<none\>|PT1M |Yes|
|**Billable Trigger Executions**<br><br>Number of workflow trigger executions getting billed. |`BillableTriggerExecutions` |Count |Total |\<none\>|PT1M |Yes|
|**Billing Usage for Native Operation Executions**<br><br>Number of native operation executions getting billed. |`BillingUsageNativeOperation` |Count |Total |\<none\>|PT1M |Yes|
|**Billing Usage for Standard Connector Executions**<br><br>Number of standard connector executions getting billed. |`BillingUsageStandardConnector` |Count |Total |\<none\>|PT1M |Yes|
|**Billing Usage for Storage Consumption Executions**<br><br>Number of storage consumption executions getting billed. |`BillingUsageStorageConsumption` |Count |Total |\<none\>|PT1M |Yes|
|**Run Failure Percentage**<br><br>Percentage of workflow runs failed. |`RunFailurePercentage` |Percent |Total |\<none\>|PT1M |Yes|
|**Run Latency**<br><br>Latency of completed workflow runs. |`RunLatency` |Seconds |Average |\<none\>|PT1M |Yes|
|**Runs Cancelled**<br><br>Number of workflow runs cancelled. |`RunsCancelled` |Count |Total |\<none\>|PT1M |Yes|
|**Runs Completed**<br><br>Number of workflow runs completed. |`RunsCompleted` |Count |Total |\<none\>|PT1M |Yes|
|**Runs Failed**<br><br>Number of workflow runs failed. |`RunsFailed` |Count |Total |\<none\>|PT1M |Yes|
|**Runs Started**<br><br>Number of workflow runs started. |`RunsStarted` |Count |Total |\<none\>|PT1M |Yes|
|**Runs Succeeded**<br><br>Number of workflow runs succeeded. |`RunsSucceeded` |Count |Total |\<none\>|PT1M |Yes|
|**Run Start Throttled Events**<br><br>Number of workflow run start throttled events. |`RunStartThrottledEvents` |Count |Total |\<none\>|PT1M |Yes|
|**Run Success Latency**<br><br>Latency of succeeded workflow runs. |`RunSuccessLatency` |Seconds |Average |\<none\>|PT1M |Yes|
|**Run Throttled Events**<br><br>Number of workflow action or trigger throttled events. |`RunThrottledEvents` |Count |Total |\<none\>|PT1M |Yes|
|**Total Billable Executions**<br><br>Number of workflow executions getting billed. |`TotalBillableExecutions` |Count |Total |\<none\>|PT1M |Yes|
|**Trigger Fire Latency**<br><br>Latency of fired workflow triggers. |`TriggerFireLatency` |Seconds |Average |\<none\>|PT1M |Yes|
|**Trigger Latency**<br><br>Latency of completed workflow triggers. |`TriggerLatency` |Seconds |Average |\<none\>|PT1M |Yes|
|**Triggers Completed**<br><br>Number of workflow triggers completed. |`TriggersCompleted` |Count |Total |\<none\>|PT1M |Yes|
|**Triggers Failed**<br><br>Number of workflow triggers failed. |`TriggersFailed` |Count |Total |\<none\>|PT1M |Yes|
|**Triggers Fired**<br><br>Number of workflow triggers fired. |`TriggersFired` |Count |Total |\<none\>|PT1M |Yes|
|**Triggers Skipped**<br><br>Number of workflow triggers skipped. |`TriggersSkipped` |Count |Total |\<none\>|PT1M |Yes|
|**Triggers Started**<br><br>Number of workflow triggers started. |`TriggersStarted` |Count |Total |\<none\>|PT1M |Yes|
|**Triggers Succeeded**<br><br>Number of workflow triggers succeeded. |`TriggersSucceeded` |Count |Total |\<none\>|PT1M |Yes|
|**Trigger Success Latency**<br><br>Latency of succeeded workflow triggers. |`TriggerSuccessLatency` |Seconds |Average |\<none\>|PT1M |Yes|
|**Trigger Throttled Events**<br><br>Number of workflow trigger throttled events. |`TriggerThrottledEvents` |Count |Total |\<none\>|PT1M |Yes|