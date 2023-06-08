---
title: Azure Monitor Logs reference - AWSCloudWatch
description: Reference for AWSCloudWatch table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
---

# AWSCloudWatch

 The CloudWatch Logs provide performance and billing data from the AWS CloudWatch service which helps the user better understand and operate the AWS system and application.

## Categories

- Security
## Solutions

- Microsoft Sentinel




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real |  |
| _IsBillable | string |  |
| Message | string | The data contained within logs from CloudWatch. |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the event was generated. |
| Type | string | The name of the table |
