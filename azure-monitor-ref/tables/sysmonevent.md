---
title: Azure Monitor Logs reference - SysmonEvent
description: Reference for SysmonEvent table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# SysmonEvent

 

## Categories

- Security
## Solutions

- Security and Audit




## Columns

|Column|Type|Description|
|---|---|---|
|TimeGenerated|datetime||
|SourceSystem|string||
|Computer|string||
|ComputerEnvironment|string||
|SubscriptionId|string||
|ResourceGroup|string||
|ResourceProvider|string||
|Resource|string||
|ResourceId|string||
|ResourceType|string||
|SysmonEventID|int||
|Activity|string||
|ProcessGuid|string||
|ProcessID|int||
|Image|string||
|User|string||
|SHA1Hash|string||
|SHA256Hash|string||
|MD5Hash|string||
|Imphash|string||
|CmdLine|string||
|CurrentDirectory|string||
|LogonGuid|string||
|LogonId|string||
|TerminalSessionId|int||
|IntegrityLevel|string||
|ParentProcessGuid|string||
|ParentProcessId|string||
|ParentImage|string||
|ParentCommandLine|string||
|TargetFilename|string||
|CreationUtcTime|datetime||
|PreviousCreationUtcTime|datetime||
|Protocol|string||
|Initiated|bool||
|SourceIsIpv6|bool||
|SourceIp|string||
|SourceHostname|string||
|SourcePort|int||
|SourcePortName|string||
|DestinationIsIpv6|bool||
|DestinationIp|string||
|DestinationHostname|string||
|DestinationPort|int||
|DestinationPortName|string||
|SysmonState|string||
|Version|string||
|SchemaVersion|string||
|ImageLoaded|string||
|Signed|string||
|SignedBy|string||
|SignatureStatus|string||
|SourceProcessGuid|string||
|SourceProcessID|int||
|SourceImage|string||
|TargetProcessGuid|string||
|TargetProcessID|int||
|TargetImage|string||
|NewThreadId|long||
|StartAddress|string||
|StartModule|string||
|StartFunction|string||
|SourceThreadId|long||
|GrantedAccess|string||
|CallTrace|string||
|Device|string||
|SysmonEventType|string||
|TargetObject|string||
|Details|string||
|NewName|string||
|Configuration|string||
|PipeName|string||
|ID|string||
|Description|string||
|Type|string||
