---
title: Azure Monitor Logs reference - DnsEvents
description: Reference for DnsEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# DnsEvents

 

## Categories

- Network
## Solutions

- DNS Analytics (Preview)
## Resource types

- Virtual machines
- VMware
- Azure Stack HCI
- System Center Virtual Machine Manager




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ClientIP | string |  |
| Computer | string |  |
| Confidence | string |  |
| Description | string |  |
| EventId | int |  |
| IndicatorThreatType | string |  |
| IPAddresses | string |  |
| MaliciousIP | string |  |
| Message | string |  |
| Name | string |  |
| QueryType | string |  |
| RemoteIPCountry | string |  |
| RemoteIPLatitude | real |  |
| RemoteIPLongitude | real |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Result | string |  |
| ResultCode | int |  |
| Severity | int |  |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| SubType | string |  |
| TaskCategory | string |  |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
