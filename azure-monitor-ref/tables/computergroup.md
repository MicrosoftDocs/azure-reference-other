---
title: Azure Monitor Logs reference - ComputerGroup
description: Reference for ComputerGroup table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# ComputerGroup

 Computer groups that can be used to scope log queries to a set of computers. Includes the computers in each group.

## Categories

- Azure Monitor
- Virtual Machines
- IT & Management Tools
## Solutions

- LogManagement
## Resource types

- Virtual machine




## Columns

|Column|Type|Description|
|---|---|---|
|SourceSystem|string|OpsManager for all records of this type.|
|TimeGenerated|datetime|Date and time the computer group was created or updated.|
|Computer|string|Name of the member computer.|
|Group|string|Name of the group.|
|GroupId|string|ID of the group.|
|GroupSourceName|string|Name of the source that the group was collected from. For Active Directory this is the domain name.|
|GroupSource|string|Source that group was collected from. Possible values are ActiveDirectory WSUSWSUSClientTargeting.|
|GroupFullName|string|Full path to the group including the source and source name.|
|Type|string||
|_ResourceId|string||
