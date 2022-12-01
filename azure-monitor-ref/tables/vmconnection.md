---
title: Azure Monitor Logs reference - VMConnection
description: Reference for VMConnection table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/1/2022
---

# VMConnection

 Traffic for inbound and outbound connections to and from monitored computers.

## Categories

- Virtual Machines
## Solutions

- AzureResources
- InfrastructureInsights
- Service Map
- Azure Monitor for VMs
## Resource types

- Virtual machines
- VMware
- Azure Stack HCI
- System Center Virtual Machine Manager
- Virtual Machine Scale Sets




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AgentId | string | Unique agent GUID for the agent reporting data on the server. |
| BytesReceived | long | Total number of bytes that have been received during the reporting time window. |
| BytesSent | long | Total number of bytes that have been sent during the reporting time window. |
| Computer | string | Name of the server from the ServiceMapComputer_CL table. |
| Confidence | string | Values are 0 - 100. |
| ConnectionId | string | Unique Id for the connection record. |
| Description | string | Description of the observed threat. |
| DestinationIp | string | IP address of the destination. |
| DestinationPort | int | Port number of the destination. |
| Direction | string | Direction of the connection value is inbound or outbound |
| FirstReportedDateTime | string | The first time the provider reported the indicator. |
| IndicatorThreatType | string | Threat indicator detected. Possible values are Botnet C2 CryptoMining Darknet DDos MaliciousUrl Malware Phishing Proxy PUA Watchlist. |
| IsActive | string | The last time the indicator was seen by Interflow. |
| LastReportedDateTime | string | Indicates indicators are deactivated with True or False value. |
| LinksEstablished | long | Number of physical network connections that have been established during the reporting time window. |
| LinksFailed | long | Number of physical network connections that have failed during the reporting time window. This information is currently available only for outbound connections. |
| LinksLive | long | Number of physical network connections that were open at the end of the reporting time window. |
| LinksTerminated | long | Number of physical network connections that have been terminated during the reporting time window. |
| Machine | string | FQDN of the computer. |
| MaliciousIp | string | Remote IP address. |
| Process | string | Identity of process or groups of processes initiating or accepting the connection. |
| ProcessName | string | Unique identifier for the process in the ServiceMapProcess_CL table. |
| Protocol | string | Protocol used for the connection. Only possible value is tcp. |
| RemoteClassification | string | A classification of the remote endpoint based on its ip and dns names and the corresponding Azure service. |
| RemoteCountry | string | Name of the country or region hosting RemoteIp. |
| RemoteDnsCanonicalNames | string | A JSON array of canonical names that came back from the DNS server. For example when using traffic manager you issue a question to foo.trafficmanage.net and get a canonical name as something.myservice.com together with an ip address. |
| RemoteDnsQuestions | string | A JSON array of DNS questions (lookups) that were performed on the machine and resolved to the RemoteIp listed in the record. |
| RemoteIp | string | The IP address of the remote end of a connection is included in the RemoteIp property. For inbound connections RemoteIp is the same as SourceIp while for outbound connections it is the same as DestinationIp. |
| RemoteLatitude | real | Geolocation latitude. An example would be 47.68. |
| RemoteLongitude | real | Geolocation longitude. An example would be -122.12. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Responses | long | Number of responses observed during the reporting time window. |
| ResponseTimeMax | long | Largest response time observed during the reporting time window in milliseconds. If no value the property is blank. |
| ResponseTimeMin | long | Smallest response time observed during the reporting time windowin milliseconds. If no value the property is blank. |
| ResponseTimeSum | long | Sum of all response times observed during the reporting time window in milliseconds. If no value the property is blank. |
| Severity | int | Possible values are 0 - 5 where 5 is the most severe and 0 is not severe at all. Default value is 3. |
| SourceIp | string | IP address of the source. |
| SourceSystem | string | Value is OpsManager for all records. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime | Date and time the record was created. |
| TLPLevel | string | Traffic Light Protocol (TLP) Level. Possible values are White Green Amber Red. |
| Type | string | The name of the table |
