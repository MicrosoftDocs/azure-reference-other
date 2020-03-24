---
title: Azure Monitor Logs reference - ContainerLog
description: Reference for ContainerLog table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# ContainerLog

 Log lines collected from stdout and stderr streams for containers.

## Categories

- Containers
- Applications
## Solutions

- ContainerInsights
- Container Monitoring Solution
## Resource types

- Kubernetes Services




## Columns

|Column|Type|Description|
|---|---|---|
|SourceSystem|string|Deprecated.|
|TimeGenerated|datetime|Date and time the record was created.|
|Computer|string|Computer/node that's generating the log.|
|TimeOfCommand|datetime|Time that the agent processed the log. This is an optional field mainly useful for troubleshooting latency issues on the agent.|
|ContainerID|string|Container ID for log source as seen by Docker engine.|
|Image|string|Container Image for log source as seen by Docker engine.|
|ImageTag|string|Used by Container solution only. Not populated by Azure Monitor for Containers.|
|Repository|string|Used by Container solution only. Not populated by Azure Monitor for Containers.|
|Name|string|Unique name of the container the form  PODUid/ContainerName.|
|LogEntry|string|Actual log line.|
|LogEntrySource|string|Source of the log line. Possible values are stdout or stderr.|
|Type|string||
|_ResourceId|string||
