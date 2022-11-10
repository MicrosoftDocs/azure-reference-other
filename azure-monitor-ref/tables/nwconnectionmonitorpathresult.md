---
title: Azure Monitor Logs reference - NWConnectionMonitorPathResult
description: Reference for NWConnectionMonitorPathResult table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# NWConnectionMonitorPathResult

 Connection Monitor path result records.

## Categories

- Network
## Solutions

- LogManagement
## Resource types

- Network Watcher - Connection Monitor




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AdditionalData | string | The additional data for the test |
| AvgRoundTripTimeMs | real | The average round trip time for the test |
| ChecksFailed | int | The total number of checks failed under the test |
| ChecksFailedPercentThreshold | int | The checks failed percent threshold set for the test |
| ChecksTotal | int | The total number of checks done under the test |
| ConnectionMonitorResourceId | string | The connection monitor resource id of the test |
| DestinationAddress | string | The address of the destination configured for the test |
| DestinationAgentId | string | The destination agent id |
| DestinationIP | string | The IP address of the destination |
| DestinationName | string | The destination end point name |
| DestinationPort | int | The destination port configured for the test |
| DestinationResourceId | string | The resource id of the Destination machine |
| DestinationSubnet | string | If applicable, the subnet of the destination |
| DestinationType | string | The type of the destination machine configured for the test |
| HopAddresses | string | The hop addresses identified for the test |
| HopLinkTypes | string | The hop link types identified for the test |
| HopResourceIds | string | The hop resource ids identified for the test |
| Hops | string | The hops identified for the test |
| HopTypes | string | The hop types identified for the test |
| Issues | string | The issues identified for the test |
| JitterMs | real | The mean deviation round trip time for the test |
| MaxRoundTripTimeMs | real | The maximum round trip time for the test |
| MinRoundTripTimeMs | real | The minimum round trip time (ms) for the test |
| PathTestResult | string | The result of the test |
| PathTestResultCriterion | string | The result criterion of the test |
| Protocol | string | The protocol of the test |
| RecordId | string | The record id for unique identification of test result record |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RoundTripTimeMsThreshold | real | The round trip threshold (ms) set for the test |
| SourceAddress | string | The address of the source configured for the test |
| SourceAgentId | string | The source agent id |
| SourceIP | string | The IP address of the source |
| SourceName | string | The source end point name |
| SourceResourceId | string | The resource id of the source machine |
| SourceSubnet | string | The subnet of the source |
| SourceSystem | string |  |
| SourceType | string | The type of the source machine configured for the test |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TestConfigurationName | string | The test configuration name to which the test belongs to |
| TestGroupName | string | The test group name to which the test belongs to |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| TopologyId | string | The topology id of the path record |
| Type | string | The name of the table |
