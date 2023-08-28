---
title: Azure Monitor Logs reference - AWSCloudWatch
description: Reference for AWSCloudWatch table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 08/28/2023
---

# AWSCloudWatch

The CloudWatch Logs provide performance and billing data from the AWS CloudWatch service which helps the user better understand and operate the AWS system and application.

## Categories

- Security
## Solutions

- SecurityInsights




## Columns

| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| ExtractedTime | datetime | The timestamp (UTC) of when the event was generated. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Message | string | The data contained within logs from CloudWatch. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) when the event was generated and equals to 'ExtractedTime' when included in message. If timestamp is missing, it’s set to the ingestion time. |
| Type | string | The name of the table |
