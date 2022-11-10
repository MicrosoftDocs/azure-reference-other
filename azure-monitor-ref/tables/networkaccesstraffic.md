---
title: Azure Monitor Logs reference - NetworkAccessTraffic
description: Reference for NetworkAccessTraffic table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# NetworkAccessTraffic

 This table is part of Identity and Network Access which contains Network Traffic Access logs. These logs can be leveraged for policy, risk and traffic management as well as to monitor users experience.

## Categories

- Security
- Network
- IT & Management Tools
## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| DstAppId | string | The ID of the destination application, as reported by the reporting device. |
| DstAppName | string | The name of the destination application. |
| DstAppType | string | The type of the application authorizing on behalf of the Actor. |
| DstBytes | int | The number of bytes sent from the destination to the source for the connection or session. |
| DstDomainType | string | The type of the destination domain. |
| DstFQDN | string | The destination device hostname, including domain information when available. |
| DstIpAddr | string | The IP address of the connection or session destination. |
| DstPortNumber | int | The destination IP port. |
| DvcAction | string | The action taken on the network session. |
| FileContentType | string | File type such as Zip, Gzip, Mp4, text, etc. |
| FileName | string | For HTTP uploads, the name of the uploaded file. |
| FileSHA256 | string | For HTTP uploads, the SHA256 hash of the uploaded file. |
| HttpRequestMethod | string | The HTTP method for HTTP/HTTPS network sessions. |
| HttpStatusCode | string | The HTTP status code for HTTP/HTTPS network sessions. |
| NetworkApplicationProtocol | string | The application layer protocol used by the connection or session. |
| NetworkDirection | string | The direction of the connection or session, into or out of the organization. |
| NetworkProtocol | string | The IP protocol used by the connection or session as listed in IANA protocol assignment. |
| Reason | string | The reason for the action. |
| RuleName | string | The name of the rule for which the request was denied. |
| RuleType | string | The rule type for which the request was. |
| SourceSystem | string |  |
| SrcBytes | int | The number of bytes sent from the source to the destination for the connection or session. |
| SrcDvcId | string | The ID of the source device as reported in the record. |
| SrcHostname | string | The source device hostname. |
| SrcIpAddr | string | The IP address from which the connection or session originated. |
| SrcPortNumber | int | The IP port from which the connection originated. |
| SrcUserId | string | A machine-readable, alphanumeric, unique representation of the source user. |
| SrcUsername | string | The source username, including domain information when available. |
| SSLDecrypted | bool | Was the transaction SSL inspected. |
| TenantId | string |  |
| TimeGenerated | datetime | Time of original event generation in UTC client time generated. |
| TimeProcessed | int | The time in milliseconds until response was received for the particular request. |
| Type | string | The name of the table |
| Url | string | For HTTP/HTTPS network sessions, the full HTTP request URL, including parameters. |
| UrlCategory | string | The defined grouping of a URL or the domain part of the URL. |
| UserAgent | string | The HTTP user agent header for HTTP/HTTPS network sessions. |
