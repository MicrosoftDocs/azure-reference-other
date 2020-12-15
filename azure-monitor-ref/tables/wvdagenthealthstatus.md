---
title: Azure Monitor Logs reference - WVDAgentHealthStatus
description: Reference for WVDAgentHealthStatus table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/9/2020
---

# WVDAgentHealthStatus

 Windows Virtual Desktop Agent Health Status.

## Solutions

- LogManagement
## Resource types

- Windows Virtual Desktop Agent Health Status




## Columns

|Column|Type|Description|
|---|---|---|
|AgentVersion|string|The version of the WVD Agent running on the Virtual Machine|
|EndpointState|string|The current state of the VM, whether its available or offline|
|LastHeartBeat|datetime|The time recorded when there was a change in the health status|
|LastUpgradeTimeStamp|datetime|The time recorded when there was a change in the health status|
|OperationName|string|The name of the operation|
|OSVersion|string|The version of the operating system|
|SessionHostHealthCheckResult|dynamic|The set of results on health checks|
|SessionHostName|string|Name of the Virtual Machine|
|SessionHostResourceId|string|The ARM path of the session host|
|SourceSystem|string||
|SxSStackVersion|string|The version of the reverse connect listener running on the VM|
|TenantId|string||
|TimeGenerated|datetime|Date and time when the report was generated (UTC)|
|Type|string|The name of the table|
|UpgradeErrorMsg|string|The version of the reverse connect listener running on the VM|
|UpgradeState|string|The last known state from a previous update|
