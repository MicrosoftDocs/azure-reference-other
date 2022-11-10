---
title: Azure Monitor Logs reference - AlertInfo
description: Reference for AlertInfo table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# AlertInfo

 Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categorization.

## Solutions

- Microsoft Sentinel




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AlertId | string | Unique identifier for the alert |
| AttackTechniques | string | MITRE ATT&CK techniques associated with the activity that triggered the alert |
| Category | string | Type of threat indicator or breach activity identified by the alert |
| DetectionSource | string | Detection technology or sensor that identified the notable component or activity |
| ServiceSource | string | Product or service that provided the alert information |
| Severity | string | Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert |
| SourceSystem | string |  |
| TenantId | string |  |
| TimeGenerated | datetime | Date and time (UTC) when the record was generated |
| Title | string | Title of the alert |
| Type | string | The name of the table |
