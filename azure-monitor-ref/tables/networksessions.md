---
title: Azure Monitor Logs reference - NetworkSessions
description: Reference for NetworkSessions table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# NetworkSessions

 Network connections or sessions such as those logged by firewalls, Wire Data, NSG, Netflow, proxy systems and web security gateways.

## Categories

- Security
## Solutions

- Microsoft Sentinel




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AdditionalFields | dynamic | When no respective column in the schema matches, additional fields can be stored in a JSON bag. |
| CloudAppId | string | The ID of the destination application for an HTTP application as identified by a proxy. This value is usually specific to the proxy used. |
| CloudAppName | string | The name of the destination application for an HTTP application as identified by a proxy. |
| CloudAppOperation | string | The operation the user performed in the context of the destination application for an HTTP application as identified by a proxy. This value is usually specific to the proxy used. |
| CloudAppRiskLevel | string | The risk level associated with an HTTP application as identified by a proxy. This value is usually specific to the proxy used. |
| DstBytes | long | The number of bytes sent from the destination to the source for the connection or session. |
| DstDomainHostname | string | The domain of the destination host. |
| DstDvcDomain | string | The Domain of the destination device. |
| DstDvcFqdn | string | The fully qualified domain name of the host where the log was created. |
| DstDvcHostname | string | The device name of the destination device. |
| DstDvcIpAddr | string | The destination IP address of a device that is not directly associated with the network packet. |
| DstDvcMacAddr | string | The destination MAC address of a device that is not directly associated with the network packet. |
| DstGeoCity | string | The city associated with the destination IP address. |
| DstGeoCountry | string | The country associated with the source IP address. |
| DstGeoLatitude | real | The latitude of the geographical coordinate associated with the destination IP address. |
| DstGeoLongitude | real | The longitude of the geographical coordinate associated with the destination IP address |
| DstGeoRegion | string | The region within a country associated with the destination IP address. |
| DstInterfaceGuid | string | GUID of the network interface which was used for authentication request. |
| DstInterfaceName | string | The network interface used for the connection or session by the destination device. |
| DstIpAddr | string | The IP address of the connection or session destination. |
| DstMacAddr | string | The MAC address of the network interface at which the connection or session terminated. |
| DstNatIpAddr | string | If reported by an intermediary NAT device such as a firewall, the IP address used by the NAT device for communication with the source. |
| DstNatPortNumber | int | If reported by an intermediary NAT device such as a firewall, the port used by the NAT device for communication with the source. |
| DstPackets | long | The number of packets sent from the destination to the source for the connection or session. The meaning of a packet is defined by the reporting device. |
| DstPortNumber | int | The destination IP port. |
| DstResourceId | string | The resource Id of the destination device. |
| DstUserAadId | string | The Azure AD account object ID of the user at the destination end of the session. |
| DstUserDomain | string | The domain or computer name of the account at the destination of the session. |
| DstUserName | string | The username of the identity associated with the session’s destination. |
| DstUserSid | string | The User ID of the identity associated with the session's destination. Typically, the identity used to authenticate a server. |
| DstUserUpn | string | The UPN of the identity associated with the session’s destination. |
| DstZone | string | The network zone of the destination, as defined by the reporting device. |
| DvcAction | string | If reported by an intermediary device such as a firewall, the action taken by device. |
| DvcHostname | string | The device name of the device generating the message. |
| DvcInboundInterface | string | If reported by an intermediary device such as a firewall, the network interface used by it for the connection to the source device. |
| DvcIpAddr | string | The IP address of the device generating the record. |
| DvcMacAddr | string | The MAC address of the network interface of the reporting device from which the event was sent. |
| DvcOutboundInterface | string | If reported by an intermediary device such as a firewall, the network interface used by it for the connection to the destination device. |
| EventCount | int | The number of events aggregated, if applicable. |
| EventEndTime | datetime | The time in which the event ended. |
| EventMessage | string | A general message or description, either included in, or generated from the record. |
| EventOriginalUid | string | The record ID from the reporting device. |
| EventProduct | string | The product generating the event. |
| EventProductVersion | string | The version of the product generating the event. |
| EventReportUrl | string | A link to the full report created by the reporting device. |
| EventResourceId | string | The resource ID of the device generating the message. |
| EventResult | string | The result reported for the activity. Empty value when not applicable. |
| EventResultDetails | string | Reason for the result reported in EventResult |
| EventSchemaVersion | string | Azure Sentinel Schema Version. |
| EventSeverity | string | If the activity reported has a security impact, denotes the severity of the impact. |
| EventStartTime | datetime | The time in which the event stated. |
| EventSubType | string | Additional description of type if applicable. |
| EventTimeIngested | datetime | The time the event was ingested to Azure Sentinel. Will be added by Azure Sentinel. |
| EventType | string | Type of event being collected. |
| EventUid | string | Unique identifier used by Sentinel to mark a row. |
| EventVendor | string | The vendor of the product generating the event. |
| FileExtension | string | The type of the file transmitted over the network connections for protocols such as FTP and HTTP. |
| FileHashMd5 | string | The MD5 hash value of the file transmitted over the network connections for protocols. |
| FileHashSha1 | string | The SHA1 hash value of the file transmitted over the network connections for protocols. |
| FileHashSha256 | string | The SHA256 hash value of the file transmitted over the network connections for protocols. |
| FileHashSha512 | string | The SHA512 hash value of the file transmitted over the network connections for protocols. |
| FileMimeType | string | The MIME type of the file transmitted over the network connections for protocols such as FTP and HTTP. |
| FileName | string | The filename transmitted over the network connections for protocols such as FTP and HTTP which provide the file name information. |
| FilePath | string | The full path, including file name, of the file. |
| FileSize | int | The file size, in bytes, of the file transmitted over the network connections for protocols. |
| HttpContentType | string | The HTTP Response content type header for HTTP/HTTPS network sessions. |
| HttpReferrerOriginal | string | The HTTP referrer header for HTTP/HTTPS network sessions. |
| HttpRequestMethod | string | The HTTP Method for HTTP/HTTPS network sessions. |
| HttpRequestTime | int | The amount of time it took to send the request to the server, if applicable. |
| HttpRequestXff | string | The HTTP X-Forwarded-For header for HTTP/HTTPS network sessions. |
| HttpResponseTime | int | The amount of time it took to receive a response in the server, if applicable. |
| HttpStatusCode | string | The HTTP Status Code for HTTP/HTTPS network sessions. |
| HttpUserAgentOriginal | string | The HTTP user agent header for HTTP/HTTPS network sessions. |
| HttpVersion | string | The HTTP Request Version for HTTP/HTTPS network connections. |
| NetworkApplicationProtocol | string | The application layer protocol used by the connection or session. |
| NetworkBytes | long | Number of bytes sent in both directions. If both BytesReceived and BytesSent exist, BytesTotal should equal their sum. |
| NetworkDirection | string | The direction the connection or session, into or out of the organization. |
| NetworkDuration | int | The amount of time, in millisecond, for the completion of the network session or connection. |
| NetworkIcmpCode | int | For an ICMP message, ICMP message type numeric value (RFC 2780 or RFC 4443). |
| NetworkIcmpType | string | For an ICMP message, ICMP message type text representation (RFC 2780 or RFC 4443). |
| NetworkPackets | long | Number of packets sent in both directions. If both PacketsReceived and PacketsSent exist, BytesTotal should equal their sum. |
| NetworkProtocol | string | The IP protocol used by the connection or session. Typically, TCP, UDP or ICMP. |
| NetworkRuleName | string | The name or ID of the rule by which DeviceAction was decided upon. |
| NetworkRuleNumber | int | Matched rule number. |
| NetworkSessionId | string | The session identifier as reported by the reporting device. |
| SourceSystem | string |  |
| SrcBytes | long | The number of bytes sent from the source to the destination for the connection or session. |
| SrcDvcDomain | string | Domain of the device from which session was initiated. |
| SrcDvcFqdn | string | The fully qualified domain name of the host where the log was created. |
| SrcDvcHostname | string | The device name of the source device. |
| SrcDvcIpAddr | string | The source IP address of a device not directly associated with the network packet (collected by a provider or explicitly calculated). |
| SrcDvcMacAddr | string | The source MAC address of a device that is not directly associated with the network packet. |
| SrcDvcModelName | string | The model of the source device. |
| SrcDvcModelNumber | string | The model number of the source device. |
| SrcDvcOs | string | The OS of the source device. |
| SrcDvcType | string | The type of the source device. |
| SrcGeoCity | string | The city associated with the source IP address. |
| SrcGeoCountry | string | The country associated with the source IP address. |
| SrcGeoLatitude | real | The latitude of the geographical coordinate associated with the source IP address. |
| SrcGeoLongitude | real | The longitude of the geographical coordinate associated with the source IP address. |
| SrcGeoRegion | string | The region within a country associated with the source IP address. |
| SrcInterfaceGuid | string | GUID of the network interface used. |
| SrcInterfaceName | string | The network interface used for the connection or session by the source device. |
| SrcIpAddr | string | The IP address from which the connection or session originated. |
| SrcMacAddr | string | The MAC address of the network interface from which the connection od session originated. |
| SrcNatIpAddr | string | If reported by an intermediary NAT device such as a firewall, the IP address used by the NAT device for communication with the destination. |
| SrcNatPortNumber | int | If reported by an intermediary NAT device such as a firewall, the port used by the NAT device for communication with the destination. |
| SrcPackets | long | The number of packets sent from the source to the destination for the connection or session. The meaning of a packet is defined by the reporting device. |
| SrcPortNumber | int | The IP port from which the connection originated. May not be relevant for a session comprising multiple connections. |
| SrcResourceId | string | The resource ID of the device generating the message. |
| SrcUserAadId | string | The Azure AD account object ID of the user at the source end of the session. |
| SrcUserDomain | string | The domain for the account initiating the session. |
| SrcUserName | string | The username of the identity associated with the sessions source. Typically, user performing an action on the client. |
| SrcUserSid | string | The user ID of the identity associated with the sessions source. Typically, user performing an action on the client. |
| SrcUserUpn | string | UPN of the account initiating the session. |
| SrcZone | string | The network zone of the source, as defined by the reporting device. |
| TenantId | string |  |
| ThreatCategory | string | The category of a threat identified by a security system such as Web Security Gateway of an IPS and is associated with this network session. |
| ThreatId | string | The ID of a threat identified by a security system such as Web Security Gateway of an IPS and is associated with this network session. |
| ThreatName | string | The name of the threat or malware identified. |
| TimeGenerated | datetime | The time the event occurred, as reported by reporting source. |
| Type | string | The name of the table |
| UrlCategory | string | The defined grouping of a URL (or could be just based on the domain in the URL) related to what it is (i.e.: adult, news, advertising, parked domains, etc.). |
| UrlHostname | string | The domain part of an HTTP request URL for HTTP/HTTPS network sessions. |
| UrlOriginal | string | The HTTP request URL for HTTP/HTTPS network sessions. |
