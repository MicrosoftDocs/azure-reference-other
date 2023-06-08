---
title: Azure Monitor Logs reference - WindowsFirewall
description: Reference for WindowsFirewall table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
---

# WindowsFirewall

 

## Categories

- Security
## Solutions

- Security and Audit
- WindowsFirewall
## Resource types

- Virtual machines
- VMware
- Azure Stack HCI
- System Center Virtual Machine Manager
- Virtual Machine Scale Sets




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real |  |
| CommunicationDirection | string |  |
| Computer | string |  |
| Confidence | string |  |
| Description | string |  |
| DestinationIP | string |  |
| DestinationPort | int |  |
| FirewallAction | string |  |
| FirstReportedDateTime | string |  |
| FullDestinationAddress | string |  |
| IndicatorThreatType | string |  |
| Info | string |  |
| IsActive | string |  |
| _IsBillable | string |  |
| LastReportedDateTime | string |  |
| MaliciousIP | string |  |
| MaliciousIPCountry | string |  |
| MaliciousIPLatitude | real |  |
| MaliciousIPLongitude | real |  |
| ManagementGroupName | string |  |
| Protocol | string |  |
| RemoteIP | string |  |
| RequestSizeInBytes | long |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Severity | int |  |
| SourceIP | string |  |
| SourcePort | int |  |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime |  |
| TLPLevel | string |  |
| Type | string | The name of the table |
