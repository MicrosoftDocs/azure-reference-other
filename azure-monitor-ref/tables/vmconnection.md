---
title: Azure Monitor Logs reference - VMConnection
description: Reference for VMConnection table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 2/20/2020
---

# VMConnection

 Traffic for inbound and outbound connections to and from monitored computers.

## Columns

|Column|Type|Description|
|---|---|---|
|TimeGenerated|datetime|Date and time the record was created.|
|Computer|string|Name of the server from the ServiceMapComputer_CL table.|
|Direction|string|Direction of the connection value is inbound or outbound|
|ProcessName|string|Unique identifier for the process in the ServiceMapProcess_CL table.|
|SourceIp|string|IP address of the source.|
|DestinationIp|string|IP address of the destination.|
|DestinationPort|int|Port number of the destination.|
|Protocol|string|Protocol used for the connection. Only possible value is tcp.|
|RemoteIp|string|The IP address of the remote end of a connection is included in the RemoteIp property. For inbound connections RemoteIp is the same as SourceIp while for outbound connections it is the same as DestinationIp.|
|RemoteDnsQuestions|string|A JSON array of DNS questions (lookups) that were performed on the machine and resolved to the RemoteIp listed in the record.|
|RemoteDnsCanonicalNames|string|A JSON array of canonical names that came back from the DNS server. For example when using traffic manager you issue a question to foo.trafficmanage.net and get a canonical name as something.myservice.com together with an ip address.|
|RemoteClassification|string|A classification of the remote endpoint based on its ip and dns names and the corresponding Azure service.|
|RemoteLongitude|real|Geolocation longitude. An example would be -122.12.|
|RemoteLatitude|real|Geolocation latitude. An example would be 47.68.|
|RemoteCountry|string|Name of the country or region hosting RemoteIp.|
|BytesSent|long|Total number of bytes that have been sent during the reporting time window.|
|BytesReceived|long|Total number of bytes that have been received during the reporting time window.|
|LinksLive|long|Number of physical network connections that were open at the end of the reporting time window.|
|LinksTerminated|long|Number of physical network connections that have been terminated during the reporting time window.|
|LinksEstablished|long|Number of physical network connections that have been established during the reporting time window.|
|LinksFailed|long|Number of physical network connections that have failed during the reporting time window. This information is currently available only for outbound connections.|
|Responses|long|Number of responses observed during the reporting time window.|
|ResponseTimeSum|long|Sum of all response times observed during the reporting time window in milliseconds. If no value the property is blank.|
|ResponseTimeMin|long|Smallest response time observed during the reporting time windowin milliseconds. If no value the property is blank.|
|ResponseTimeMax|long|Largest response time observed during the reporting time window in milliseconds. If no value the property is blank.|
|MaliciousIp|string|Remote IP address.|
|IndicatorThreatType|string|Threat indicator detected. Possible values are Botnet C2 CryptoMining Darknet DDos MaliciousUrl Malware Phishing Proxy PUA Watchlist.|
|Description|string|Description of the observed threat.|
|TLPLevel|string|Traffic Light Protocol (TLP) Level. Possible values are White Green Amber Red.|
|Confidence|string|Values are 0 - 100.|
|Severity|int|Possible values are 0 - 5 where 5 is the most severe and 0 is not severe at all. Default value is 3.|
|FirstReportedDateTime|string|The first time the provider reported the indicator.|
|LastReportedDateTime|string|Indicates indicators are deactivated with True or False value.|
|IsActive|string|The last time the indicator was seen by Interflow.|
|ConnectionId|string|Unique Id for the connection record.|
|Machine|string|FQDN of the computer.|
|Process|string|Identity of process or groups of processes initiating or accepting the connection.|
|AgentId|string|Unique agent GUID for the agent reporting data on the server.|
|SourceSystem|string|Value is OpsManager for all records.|
|Type|string||
|_ResourceId|string||
