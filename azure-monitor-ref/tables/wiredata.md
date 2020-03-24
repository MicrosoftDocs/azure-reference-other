---
title: Azure Monitor Logs reference - WireData
description: Reference for WireData table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
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

- Virtual machine
- Virtual machine scale set




## Columns

|Column|Type|Description|
|---|---|---|
|Computer|string|Computer name where data was collected|
|SessionStartTime|datetime|Start time of session|
|SessionEndTime|datetime|End time of session|
|LocalIP|string|IP address of the local computer|
|LocalSubnet|string|Subnet where data was collected|
|LocalPortNumber|int|Local port number|
|RemoteIP|string|Remote IP address used by the remote computer|
|RemotePortNumber|int|Port number used by the remote IP address|
|SessionID|string|A unique value that identifies communication session between two IP addresses|
|SessionState|string|Connected or disconnected|
|SentBytes|long|Number of bytes sent|
|ReceivedBytes|long|Amount of bytes received|
|TotalBytes|long|Total number of bytes sent during session|
|ProtocolName|string|Name of the network protocol used|
|IPVersion|string|IP version|
|Direction|string|Inbound or outbound|
|ApplicationProtocol|string|Type of network protocol used|
|ProcessID|int|Windows process ID|
|ProcessName|string|Path and file name of the process|
|MaliciousIP|string|IP address of a known malicious source|
|IndicatorThreatType|string|Threat indicator detected is one of the following values Botnet C2 CryptoMining Darknet DDos MaliciousUrl Malware Phishing Proxy PUA Watchlist.|
|Description|string|Description of the observed threat.|
|TLPLevel|string|Traffic Light Protocol (TLP) Level is one of the defined values White Green Amber Red.|
|Confidence|string|Confidence level for Malicious IP identification. Values are 0 - 100.|
|Severity|int|Suspected malware severity|
|FirstReportedDateTime|string|The first time the provider reported the threat.|
|LastReportedDateTime|string|The last time the indicator was seen by Interflow.|
|IsActive|string|Indicates indicators are deactivated with True or False value.|
|RemoteIPLongitude|real|IP longitude value|
|RemoteIPLatitude|real|IP latitude value|
|RemoteIPCountry|string|Country/region of the remote IP address|
|SourceSystem|string|OpsManager|
|ManagementGroupName|string|Name of the Operations Manager management group|
|TimeGenerated|datetime|Time of the record|
|LocalMAC|string|Hold over field from old schema - attribute not collected|
|RemoteMAC|string|Hold over field from old schema - attribute not collected|
|SequenceNumber|long|Hold over field from old schema - attribute not collected|
|SentPackets|long|Hold over field from old schema - attribute not collected|
|ReceivedPackets|long|Hold over field from old schema - attribute not collected|
|ApplicationServiceName|string|Hold over field from old schema - attribute not collected|
|LatencyMilliseconds|int|Hold over field from old schema - attribute not collected|
|LatencySamplingTimeStamp|datetime|Hold over field from old schema - attribute not collected|
|LatencySamplingFailureRate|string|Hold over field from old schema - attribute not collected|
|Type|string||
|_ResourceId|string||
