---
title: Azure Monitor Logs reference - LinuxAuditLog
description: Reference for LinuxAuditLog table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# LinuxAuditLog

 

## Categories

- Security
## Solutions

- Security and Audit
- Microsoft Sentinel




## Columns

| Column | Type | Description |
| --- | --- | --- |
| a0 | string |  |
| a1 | string |  |
| a2 | string |  |
| a3 | string |  |
| a4 | string |  |
| a5 | string |  |
| a6 | string |  |
| a7 | string |  |
| a8 | string |  |
| a9 | string |  |
| acct | string |  |
| addr | string |  |
| arch | string |  |
| argc | long |  |
| AuditID | string |  |
| audit_user | string |  |
| auid | long |  |
| cmd | string |  |
| comm | string |  |
| Computer | string |  |
| ComputerEnvironment | string |  |
| cwd | string |  |
| data | string |  |
| effective_group | string |  |
| effective_user | string |  |
| egid | long |  |
| euid | long |  |
| exe | string |  |
| exit | string |  |
| ExternalAgentIp | string |  |
| family | string |  |
| filetype | string |  |
| gid | long |  |
| group | string |  |
| hostname | string |  |
| icmptype | string |  |
| key | string |  |
| ManagementGroup | string |  |
| ManagementGroupName | string |  |
| name | string |  |
| node | string |  |
| op | string |  |
| path | string |  |
| pid | long |  |
| ppid | long |  |
| RawRecord | string |  |
| RecordType | string |  |
| res | string |  |
| ResourceId | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| result | string |  |
| SerialNumber | string |  |
| ses | long |  |
| SourceComputerId | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| success | string |  |
| syscall | string |  |
| terminal | string |  |
| TimeGenerated | datetime |  |
| TimeUploaded | datetime |  |
| tty | string |  |
| Type | string | The name of the table |
| uid | long |  |
| user | string |  |
| vm | string |  |
