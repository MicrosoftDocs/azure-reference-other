---
title: Azure Monitor Logs reference - Operation
description: Reference for Operation table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 2/20/2020
---

# Operation

 Operational log of important activities affecting workspace. Includes both user-initiated activities and notifications from Log Analytics workspace services such as data-capping.

## Columns

|Column|Type|Description|
|---|---|---|
|SourceSystem|string|Value is OpsManager for all records in this table.|
|TimeGenerated|datetime|Date and time that the record was created.|
|ManagementGroupName|string|Name of the Operations Manager management group for System Center Operations Manager agents.|
|SourceComputerId|string|Unique GUID identifier for a computer.|
|OperationStatus|string|Operation status description. Ccommon values include Warning Succeeded Failed Error.|
|Computer|string|Name of a physical or virtual machine having membership with Log Analytics agent.|
|Detail|string|User friendly string that describes further details about the operation|
|OperationCategory|string|Name of the area that produced the record.|
|Solution|string|Name of the managed solution that produced the record. Can also include other sources such as RestAPI.|
|HelpLink|string|Reference URL for additional contextual information.|
|OperationKey|string|Operation ID. Can be a GUID or string.|
|ErrorId|string|Deprecated.|
|CorrelationId|string|GUID that is shared with telemetry belonging to the same uber action.|
|Type|string||
|_ResourceId|string||
