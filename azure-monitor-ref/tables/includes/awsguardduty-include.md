---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: AWSGuardDuty
---


| Column | Type | Description |
|---|---|---|
| AccountId | string | The AWS account ID of the owner of the source network interface for which traffic is recorded. If the network interface is created by an AWS service, for example when creating a VPC endpoint or Network Load Balancer, the record may display unknown for this field. |
| ActivityType | string | A formatted string representing the type of activity that triggered the finding. |
| Arn | string | Amazon resource name of the finding. |
| _BilledSize | real | The record size in bytes |
| Description | string | Description of the primary purpose of the threat or attack related to the finding. |
| Id | string | A unique Finding ID for this finding type and set of parameters. New occurrences of activity matching this pattern will be aggregated to the same ID. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Partition | string | The AWS partition in which the finding was generated. |
| Region | string | The AWS region in which the finding was generated. |
| ResourceDetails | dynamic | Gives details on the AWS resource that was targeted by the trigger activity. The information available varies based on resource type and action typ. |
| SchemaVersion | string | The Guard Duty finding version. |
| ServiceDetails | dynamic | Gives details on the AWS service that was related to the finding, including Action, Actor/Target, Evidence, Anomalous behavior and Additional information. |
| Severity | int | A finding's assigned severity level of either High, Medium, or Low. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| TenantId | string | The Log Analytics workspace ID |
| TimeCreated | datetime | The time and date when this finding was first created. If this value differs from Updated at (TimeGenerated), it indicates that the activity has occurred multiple times and is an ongoing issue. |
| TimeGenerated | datetime | The timestamp (UTC) of when the event was generated, The last time this finding was updated with new activity matching the pattern that prompted GuardDuty to generate this finding. |
| Title | string | Summary of the primary purpose of the threat or attack related to the finding. |
| Type | string | The name of the table |
