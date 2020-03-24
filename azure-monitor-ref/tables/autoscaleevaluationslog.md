---
title: Azure Monitor Logs reference - AutoscaleEvaluationsLog
description: Reference for AutoscaleEvaluationsLog table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# AutoscaleEvaluationsLog

 

## Categories

- Azure Monitor
- Virtual Machines
- Azure Resources
## Solutions

- LogManagement
## Resource types

- Azure Monitor autoscale settings




## Columns

|Column|Type|Description|
|---|---|---|
|SourceSystem|string||
|TimeGenerated|datetime||
|ResourceId|string||
|OperationName|string||
|Category|string||
|ResultType|string||
|ResultDescription|string||
|CorrelationId|string||
|TargetResourceId|string||
|AvailabilitySet|string||
|CloudServiceName|string||
|CoolDown|int||
|CurrentInstanceCount|int||
|MetricData|string||
|DefaultInstanceCount|int||
|DeploymentSlot|string||
|MetricEndTime|datetime||
|EstimateScaleResult|string||
|EvaluationResult|string||
|EvaluationTime|datetime||
|LastScaleActionOperationId|string||
|LastScaleActionOperationStatus|string||
|LastScaleActionTime|datetime||
|MaximumInstanceCount|int||
|AutoscaleMetricName|string||
|MetricNamespace|string||
|MinimumInstanceCount|int||
|NewInstanceCount|int||
|ObservedValue|real||
|Operator|string||
|Profile|string||
|ProfileEvaluationTime|datetime||
|ProfileSelected|bool||
|Projection|real||
|InstanceUpdateReason|string||
|CloudServiceRole|string||
|SelectedAutoscaleProfile|string||
|ServerFarm|string||
|ShouldUpdateInstance|bool||
|SkipCurrentAutoscaleEvaluation|bool||
|SkipRuleEvaluationForCooldown|bool||
|MetricStartTime|datetime||
|Threshold|real||
|TimeAggregationType|string||
|MetricTimeGrain|string||
|TimeGrainStatistic|string||
|TimeWindow|string||
|Webspace|string||
|Type|string||
