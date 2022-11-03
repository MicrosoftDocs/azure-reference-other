---
title: Azure Monitor Logs reference - WireData
description: Reference for WireData table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# WireData

 Network data collected by the WireData solution using by the Dependency agent and Log analytics agent.

## Categories

- Virtual Machines
- Security
## Solutions

- WireData
- Wire Data 2.0
## Resource types

- Virtual machines
- VMware
- Azure Stack HCI
- System Center Virtual Machine Manager
- Virtual Machine Scale Sets




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ApplicationProtocol | string | Type of network protocol used |
| ApplicationServiceName | string | Hold over field from old schema - attribute not collected |
| Computer | string | Computer name where data was collected |
| Confidence | string | Confidence level for Malicious IP identification. Values are 0 - 100. |
| Description | string | Description of the observed threat. |
| Direction | string | Inbound or outbound |
| FirstReportedDateTime | string | The first time the provider reported the threat. |
| IndicatorThreatType | string | Threat indicator detected is one of the following values Botnet C2 CryptoMining Darknet DDos MaliciousUrl Malware Phishing Proxy PUA Watchlist. |
| IPVersion | string | IP version |
| IsActive | string | Indicates indicators are deactivated with True or False value. |
| LastReportedDateTime | string | The last time the indicator was seen by Interflow. |
| LatencyMilliseconds | int | Hold over field from old schema - attribute not collected |
| LatencySamplingFailureRate | string | Hold over field from old schema - attribute not collected |
| LatencySamplingTimeStamp | datetime | Hold over field from old schema - attribute not collected |
| LocalIP | string | IP address of the local computer |
| LocalMAC | string | Hold over field from old schema - attribute not collected |
| LocalPortNumber | int | Local port number |
| LocalSubnet | string | Subnet where data was collected |
| MaliciousIP | string | IP address of a known malicious source |
| ManagementGroupName | string | Name of the Operations Manager management group |
| ProcessID | int | Windows process ID |
| ProcessName | string | Path and file name of the process |
| ProtocolName | string | Name of the network protocol used |
| ReceivedBytes | long | Amount of bytes received |
| ReceivedPackets | long | Hold over field from old schema - attribute not collected |
| RemoteIP | string | Remote IP address used by the remote computer |
| RemoteIPCountry | string | Country/region of the remote IP address |
| RemoteIPLatitude | real | IP latitude value |
| RemoteIPLongitude | real | IP longitude value |
| RemoteMAC | string | Hold over field from old schema - attribute not collected |
| RemotePortNumber | int | Port number used by the remote IP address |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SentBytes | long | Number of bytes sent |
| SentPackets | long | Hold over field from old schema - attribute not collected |
| SequenceNumber | long | Hold over field from old schema - attribute not collected |
| SessionEndTime | datetime | End time of session |
| SessionID | string | A unique value that identifies communication session between two IP addresses |
| SessionStartTime | datetime | Start time of session |
| SessionState | string | Connected or disconnected |
| Severity | int | Suspected malware severity |
| SourceSystem | string | OpsManager |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime | Time of the record |
| TLPLevel | string | Traffic Light Protocol (TLP) Level is one of the defined values White Green Amber Red. |
| TotalBytes | long | Total number of bytes sent during session |
| Type | string | The name of the table |
