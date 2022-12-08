---
title: Azure Monitor Logs reference - AZFWDnsQuery
description: Reference for AZFWDnsQuery table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/8/2022
---

# AZFWDnsQuery

 Contains all DNS Proxy events log data.

## Categories

- Security
## Solutions

- LogManagement
## Resource types

- Firewalls




## Columns

| Column | Type | Description |
| --- | --- | --- |
| DnssecOkBit | bool | A flag indicating that the resolver supports DNSSEC records. |
| EDNS0BufferSize | int | Client's EDNS0 buffer size. Specifies the maximum packet size allowed in responses in bytes. |
| ErrorMessage | string | Description of the error returned to the client. Empty if request is successful. |
| ErrorNumber | int | Error number matching the returned response code. |
| Protocol | string | Protocol used to send the DNS query. For example: TCP, UDP |
| QueryClass | string | DNS query's query class. |
| QueryId | int | DNS query's query ID. |
| QueryName | string | DNS query's name to resolve. |
| QueryType | string | DNS query's query type. |
| RequestDurationSecs | real | Duration of the DNS request from the time it arrived to the firewall and until a response was sent to the client. |
| RequestSize | int | The size of the DNS request in bytes. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResponseCode | string | DNS reponse code. |
| ResponseFlags | string | DNS reponse flags, comma separated. |
| ResponseSize | int | DNS reponse syze in bytes. |
| SourceIp | string | DNS query's source IP address. |
| SourcePort | int | DNS query's source Port. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Timestamp (UTC) when the data plane log was created. |
| Type | string | The name of the table |
