---
title: Azure Monitor Logs reference - Event
description: Reference for Event table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# Event

 Events from Windows Event Log on Windows computers using the Log Analytics agent.

## Categories

- Virtual Machines
## Solutions

- LogManagement
## Resource types

- Virtual machines
- VMware
- Azure Stack HCI
- System Center Virtual Machine Manager
- Virtual Machine Scale Sets
- Azure Stack HCI




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AzureDeploymentID | string | Azure deployment ID of the cloud service the log belongs to. Only populated when events are collected using Azure Diagnostics agent and collected from Azure storage. |
| Computer | string | Name of the computer that the event was collected from. |
| EventCategory | int | Category of the event. |
| EventData | string | All event data in raw format. |
| EventID | int | Number of the event. |
| EventLevel | int | Severity of the event in numeric form. |
| EventLevelName | string | Severity of the event in text form. |
| EventLog | string | Name of the event log that the event was collected from. |
| ManagementGroupName | string | Name of the management group for System Center Operations Manager agents. For other agents this value is AOI-<workspace ID> |
| Message | string | Event message for the different Languages. The language is defined by the LCID attribute. |
| ParameterXml | string | Event parameter values in XML format. |
| RenderedDescription | string | Event description with parameter values. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Role | string | Role of the cloud service the log belongs to. Only populated when events are collected using Azure Diagnostics agent and collected from Azure storage. |
| Source | string | Source of the event. |
| SourceSystem | string | Type of agent the event was collected from. Possible values are OpsManager Linux and AzureStorage. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime | Date and time the record was created. |
| Type | string | The name of the table |
| UserName | string | User name of the account that logged the event. |
