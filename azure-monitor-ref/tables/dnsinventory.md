---
title: Azure Monitor Logs reference - DnsInventory
description: Reference for DnsInventory table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# DnsInventory

 

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
| Computer | string |  |
| DnsSecSigned | string |  |
| DomainName | string |  |
| DynamicUpdate | string |  |
| ForestName | string |  |
| NameServers | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResourceRecordName | string |  |
| ResourceRecordType | string |  |
| ServerIPs | string |  |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| SubType | string |  |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
| ZoneName | string |  |
