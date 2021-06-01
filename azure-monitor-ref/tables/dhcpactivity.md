---
title: Azure Monitor Logs reference - DHCPActivity
description: Reference for DHCPActivity table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 6/1/2021
---

# DHCPActivity

 Windows DHCP Server Activity

## Categories

- Security
## Solutions

- Azure Sentinel




## Columns

|Column|Type|Description|
|---|---|---|
|Computer|string|DHCP server that produced the activity log|
|Description|string|Description of the DHCP activity|
|EventID|int|Event ID of the DHCP activity|
|HostName|string|Hostname of the DHCP client|
|IPAddress|string|IP address of the DHCP client|
|MACAddress|string|MAC address of the DHCP client|
|ManagementGroupName|string|Workspace ID from OpsManager|
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|SourceSystem|string|Source System of Solution (OpsManager)|
|_SubscriptionId|string|A unique identifier for the subscription that the record is associated with|
|TenantId|string||
|TimeGenerated|datetime|Timestamp (UTC) of the DHCP activity|
|Type|string|The name of the table|
