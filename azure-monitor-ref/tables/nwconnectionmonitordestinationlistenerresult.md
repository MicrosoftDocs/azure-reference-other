---
title: Azure Monitor Logs reference - NWConnectionMonitorDestinationListenerResult
description: Reference for NWConnectionMonitorDestinationListenerResult table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/1/2022
---

# NWConnectionMonitorDestinationListenerResult

 Connection Monitor destination listener result records.

## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ConnectionMonitorResourceId | string | The connection monitor resource id of the test |
| DestinationAddress | string | The address of the destination configured for the test |
| DestinationAgentId | string | The destination agent id |
| DestinationIP | string | The IP address of the destination |
| DestinationName | string | The destination end point name |
| DestinationPort | int | The Destination port configured for the test |
| DestinationResourceId | string | The resource id of the Destination machine |
| DestinationSubnet | string | If applicable, the subnet of the destination configured for the test |
| DestinationType | string | The type of the destination machine configured for the test |
| Issues | string | The issues identfied by Destination Listener |
| ListeningOutcome | string | The listening outcome result |
| Protocol | string | The protocol of the test |
| RecordId | string | The record id for unique identification of test result record |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TestConfigurationName | string | The test configuration name to which the test belongs to |
| TestGroupName | string | The test group name to which the test belongs to |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
