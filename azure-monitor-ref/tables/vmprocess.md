---
title: Azure Monitor Logs reference - VMProcess
description: Reference for VMProcess table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# VMProcess

 Process data for servers collected by the Service Map and VM Insights solutions using the Dependency agent and Log analytics agent.

## Categories

- Virtual Machines
## Solutions

- Service Map
- VMInsights
## Resource types

- Virtual machine
- Virtual machine scale set




## Columns

|Column|Type|Description|
|---|---|---|
|TimeGenerated|datetime|Date and time the record was created.|
|Computer|string|The name of the computer.|
|AgentId|string|Unique ID for the dependency agent installed on the server.|
|Machine|string|The machine name of the server.|
|Process|string|The name of the process.|
|ExecutableName|string|The name of the process executable|
|DisplayName|string|The friendly display name of the process|
|Role|string|The role of the process.|
|Group|string|The process group name for the process|
|StartTime|datetime|The process pool start time|
|FirstPid|int|The first PID in the process pool|
|Description|string|The process description|
|CompanyName|string|The name of the company|
|InternalName|string|The internal name|
|ProductName|string|The name of the product|
|ProductVersion|string|The product version|
|FileVersion|string|The file version|
|ExecutablePath|string|The path to the executable file|
|CommandLine|string|The command line|
|WorkingDirectory|string|The working directory|
|Services|dynamic|A list of services associated with the process.|
|UserName|string|The account under which the process is executing|
|UserDomain|string|The domain under which the process is executing|
|SourceSystem|string|The source of the data collected (OpsManager)|
|Type|string||
|_ResourceId|string||
