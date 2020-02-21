---
title: Azure Monitor Logs reference - Event
description: Reference for Event table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 2/20/2020
---

# Event

 Events from Windows Event Log on Windows computers using the Log Analytics agent.

## Columns

|Column|Type|Description|
|---|---|---|
|SourceSystem|string|Type of agent the event was collected from. Possible values are OpsManager Linux and AzureStorage.|
|TimeGenerated|datetime|Date and time the record was created.|
|Source|string|Source of the event.|
|EventLog|string|Name of the event log that the event was collected from.|
|Computer|string|Name of the computer that the event was collected from.|
|EventLevel|int|Severity of the event in numeric form.|
|EventLevelName|string|Severity of the event in text form.|
|ParameterXml|string|Event parameter values in XML format.|
|EventData|string|All event data in raw format.|
|EventID|int|Number of the event.|
|RenderedDescription|string|Event description with parameter values.|
|AzureDeploymentID|string|Azure deployment ID of the cloud service the log belongs to. Only populated when events are collected using Azure Diagnostics agent and collected from Azure storage.|
|Role|string|Role of the cloud service the log belongs to. Only populated when events are collected using Azure Diagnostics agent and collected from Azure storage.|
|EventCategory|int|Category of the event.|
|UserName|string|User name of the account that logged the event.|
|Message|string|Event message for the different Languages. The language is defined by the LCID attribute.|
|ManagementGroupName|string|Name of the management group for System Center Operations Manager agents. For other agents this value is AOI-<workspace ID>|
|Type|string||
|_ResourceId|string||
