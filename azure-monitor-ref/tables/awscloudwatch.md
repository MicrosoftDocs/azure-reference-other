---
title: Azure Monitor Logs reference - AWSCloudWatch
description: Reference for AWSCloudWatch table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 2/14/2023
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
| Message | string | The data contained within logs from CloudWatch. |
| SourceSystem | string |  |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the event was generated. |
| Type | string | The name of the table |
