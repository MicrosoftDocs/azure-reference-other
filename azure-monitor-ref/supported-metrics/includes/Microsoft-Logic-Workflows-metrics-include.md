---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Logic/Workflows, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Action Latency <p><p>Latency of completed workflow actions. |`ActionLatency` |Seconds |Average |No Dimensions|PT1M |Yes|
|Actions Completed <p><p>Number of workflow actions completed. |`ActionsCompleted` |Count |Total |No Dimensions|PT1M |Yes|
|Actions Failed <p><p>Number of workflow actions failed. |`ActionsFailed` |Count |Total |No Dimensions|PT1M |Yes|
|Actions Skipped <p><p>Number of workflow actions skipped. |`ActionsSkipped` |Count |Total |No Dimensions|PT1M |Yes|
|Actions Started <p><p>Number of workflow actions started. |`ActionsStarted` |Count |Total |No Dimensions|PT1M |Yes|
|Actions Succeeded <p><p>Number of workflow actions succeeded. |`ActionsSucceeded` |Count |Total |No Dimensions|PT1M |Yes|
|Action Success Latency <p><p>Latency of succeeded workflow actions. |`ActionSuccessLatency` |Seconds |Average |No Dimensions|PT1M |Yes|
|Action Throttled Events<p><p>Number of workflow action throttled events.. |`ActionThrottledEvents` |Count |Total |No Dimensions|PT1M |Yes|
|Billable Action Executions<p><p>Number of workflow action executions getting billed. |`BillableActionExecutions` |Count |Total |No Dimensions|PT1M |Yes|
|Billable Trigger Executions<p><p>Number of workflow trigger executions getting billed. |`BillableTriggerExecutions` |Count |Total |No Dimensions|PT1M |Yes|
|Billing Usage for Native Operation Executions<p><p>Number of native operation executions getting billed. |`BillingUsageNativeOperation` |Count |Total |No Dimensions|PT1M |Yes|
|Billing Usage for Standard Connector Executions<p><p>Number of standard connector executions getting billed. |`BillingUsageStandardConnector` |Count |Total |No Dimensions|PT1M |Yes|
|Billing Usage for Storage Consumption Executions<p><p>Number of storage consumption executions getting billed. |`BillingUsageStorageConsumption` |Count |Total |No Dimensions|PT1M |Yes|
|Run Failure Percentage<p><p>Percentage of workflow runs failed. |`RunFailurePercentage` |Percent |Total |No Dimensions|PT1M |Yes|
|Run Latency<p><p>Latency of completed workflow runs. |`RunLatency` |Seconds |Average |No Dimensions|PT1M |Yes|
|Runs Cancelled<p><p>Number of workflow runs cancelled. |`RunsCancelled` |Count |Total |No Dimensions|PT1M |Yes|
|Runs Completed<p><p>Number of workflow runs completed. |`RunsCompleted` |Count |Total |No Dimensions|PT1M |Yes|
|Runs Failed<p><p>Number of workflow runs failed. |`RunsFailed` |Count |Total |No Dimensions|PT1M |Yes|
|Runs Started<p><p>Number of workflow runs started. |`RunsStarted` |Count |Total |No Dimensions|PT1M |Yes|
|Runs Succeeded<p><p>Number of workflow runs succeeded. |`RunsSucceeded` |Count |Total |No Dimensions|PT1M |Yes|
|Run Start Throttled Events<p><p>Number of workflow run start throttled events. |`RunStartThrottledEvents` |Count |Total |No Dimensions|PT1M |Yes|
|Run Success Latency<p><p>Latency of succeeded workflow runs. |`RunSuccessLatency` |Seconds |Average |No Dimensions|PT1M |Yes|
|Run Throttled Events<p><p>Number of workflow action or trigger throttled events. |`RunThrottledEvents` |Count |Total |No Dimensions|PT1M |Yes|
|Total Billable Executions<p><p>Number of workflow executions getting billed. |`TotalBillableExecutions` |Count |Total |No Dimensions|PT1M |Yes|
|Trigger Fire Latency <p><p>Latency of fired workflow triggers. |`TriggerFireLatency` |Seconds |Average |No Dimensions|PT1M |Yes|
|Trigger Latency <p><p>Latency of completed workflow triggers. |`TriggerLatency` |Seconds |Average |No Dimensions|PT1M |Yes|
|Triggers Completed <p><p>Number of workflow triggers completed. |`TriggersCompleted` |Count |Total |No Dimensions|PT1M |Yes|
|Triggers Failed <p><p>Number of workflow triggers failed. |`TriggersFailed` |Count |Total |No Dimensions|PT1M |Yes|
|Triggers Fired <p><p>Number of workflow triggers fired. |`TriggersFired` |Count |Total |No Dimensions|PT1M |Yes|
|Triggers Skipped<p><p>Number of workflow triggers skipped. |`TriggersSkipped` |Count |Total |No Dimensions|PT1M |Yes|
|Triggers Started <p><p>Number of workflow triggers started. |`TriggersStarted` |Count |Total |No Dimensions|PT1M |Yes|
|Triggers Succeeded <p><p>Number of workflow triggers succeeded. |`TriggersSucceeded` |Count |Total |No Dimensions|PT1M |Yes|
|Trigger Success Latency <p><p>Latency of succeeded workflow triggers. |`TriggerSuccessLatency` |Seconds |Average |No Dimensions|PT1M |Yes|
|Trigger Throttled Events<p><p>Number of workflow trigger throttled events. |`TriggerThrottledEvents` |Count |Total |No Dimensions|PT1M |Yes|