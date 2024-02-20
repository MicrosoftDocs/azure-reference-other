---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: AutoscaleEvaluationsLog
---


| Column | Type | Description |
|---|---|---|
| AutoscaleMetricName | string |   |
| AvailabilitySet | string |   |
| _BilledSize | real | The record size in bytes |
| Category | string |   |
| CloudServiceName | string |   |
| CloudServiceRole | string |   |
| CoolDown | int |   |
| CorrelationId | string |   |
| CurrentInstanceCount | int |   |
| DefaultInstanceCount | int |   |
| DeploymentSlot | string |   |
| EstimateScaleResult | string |   |
| EvaluationResult | string |   |
| EvaluationTime | datetime |   |
| InstanceUpdateReason | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| LastScaleActionOperationId | string |   |
| LastScaleActionOperationStatus | string |   |
| LastScaleActionTime | datetime |   |
| MaximumInstanceCount | int |   |
| MetricData | string |   |
| MetricEndTime | datetime |   |
| MetricNamespace | string |   |
| MetricStartTime | datetime |   |
| MetricTimeGrain | string |   |
| MinimumInstanceCount | int |   |
| NewInstanceCount | int |   |
| ObservedValue | real |   |
| OperationName | string |   |
| Operator | string |   |
| Profile | string |   |
| ProfileEvaluationTime | datetime |   |
| ProfileSelected | bool |   |
| Projection | real |   |
| ResourceId | string |   |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultDescription | string |   |
| ResultType | string |   |
| SelectedAutoscaleProfile | string |   |
| ServerFarm | string |   |
| ShouldUpdateInstance | bool |   |
| SkipCurrentAutoscaleEvaluation | bool |   |
| SkipRuleEvaluationForCooldown | bool |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TargetResourceId | string |   |
| Threshold | real |   |
| TimeAggregationType | string |   |
| TimeGenerated | datetime |   |
| TimeGrainStatistic | string |   |
| TimeWindow | string |   |
| Type | string | The name of the table |
| Webspace | string |   |
