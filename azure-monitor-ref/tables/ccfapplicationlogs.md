---
title: Azure Monitor Logs reference - CCFApplicationLogs
description: Reference for CCFApplicationLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/1/2022
---

# CCFApplicationLogs

 Contains the logs generated in the CCF application.

## Categories

- Azure Resources
- Audit
## Solutions

- LogManagement
## Resource types

- Managed CCF




## Columns

| Column | Type | Description |
| --- | --- | --- |
| File | string | The file name that generated the log message. |
| Level | string | An error or informational message indicating if the service processed the request. |
| LineNumber | int | The line number in the file that the message refers to. |
| Location | string | The Azure datacenter region where the pod is deployed. |
| Message | string | The Log message. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Date and time the record was created. |
| Type | string | The name of the table |
