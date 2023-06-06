---
title: Azure Monitor Logs reference - McasShadowItReporting
description: Reference for McasShadowItReporting table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 5/26/2023
---

# McasShadowItReporting

 McasShadowItReporting

## Categories

- Security
## Solutions

- Microsoft Sentinel
- Microsoft Defender for Cloud Apps


## Columns

| Column | Type | Description |
| --- | --- | --- |
| AadTenantId | string | The unique identifier of the Azure Tenant |
| AppCategory | string | _Defined application catalogue name_ |
| AppId | string | _Unique ID of the application_ |
| AppName | string | _Name of Application_ |
| AppScore | int | _Application risk score_ |
| AppTags | dynamic | _Built-in and custom tags defined for the app _|
| BlockedEvents | int | size of blocked event |
| DownloadedBytes | int | 	Amount of downloaded data |
| EnrichedUserName | string | 	Enriched user name with Azure AD username |
| IpAddress | string | 	Source IP address |
| _IsBillable | string | Logical flag to indicate whether we bill for this data record. |
| MachineId | string | Unique identifier for the device in the service. |
| MachineName | string | Fully qualified domain name (FQDN) of the device. |
| RawUserName | string | Raw username information from source |
| RichUserName | string | enriched username information from source |
| SourceSystem | string | Source system – static value |
| StreamName | string | Name of the specific stream |
| TenantId | string | Workspace ID |
| TimeGenerated | datetime | The date and time of the event in UTC. |
| TotalBytes | int |	Total number of events per session |
| TotalEvents | int |	Total number of events per session |
| Type | string | The name of the table |
| UploadedBytes | int | Amount of uploaded data |
| UserName | string | User name of the account. |
