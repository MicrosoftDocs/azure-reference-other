---
title: Azure Monitor Logs reference - DHCPActivity
description: Reference for DHCPActivity table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 2/20/2020
---

# DHCPActivity

 Windows DHCP Server Activity

## Columns

|Column|Type|Description|
|---|---|---|
|TenantId|string||
|TimeGenerated|datetime|Timestamp (UTC) of the DHCP activity|
|ManagementGroupName|string|Workspace ID from OpsManager|
|SourceSystem|string|Source System of Solution (OpsManager)|
|Computer|string|DHCP server that produced the activity log|
|EventID|int|Event ID of the DHCP activity|
|Description|string|Description of the DHCP activity|
|IPAddress|string|IP address of the DHCP client|
|HostName|string|Hostname of the DHCP client|
|MACAddress|string|MAC address of the DHCP client|
|Type|string||
|_ResourceId|string||
