---
title: Azure Monitor Logs reference - IdentityDirectoryEvents
description: Reference for IdentityDirectoryEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# IdentityDirectoryEvents

 Captures various identity-related events, like password changes, password expiration, and user principal name (UPN) changes.

## Categories

- Security
## Solutions

- Microsoft Sentinel




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AccountDisplayName | string | Name of the account user displayed in the address book |
| AccountDomain | string | Domain of the account |
| AccountName | string | User name of the account |
| AccountObjectId | string | Unique identifier for the account in Azure AD |
| AccountSid | string | Security Identifier (SID) of the account |
| AccountUpn | string | User principal name (UPN) of the account |
| ActionType | string | Type of activity that triggered the event |
| AdditionalFields | dynamic | Additional information about the entity or event |
| Application | string | Application that performed the recorded action |
| DestinationDeviceName | string | Name of the device running the server application that processed the recorded action |
| DestinationIPAddress | string | IP address of the device running the server application that processed the recorded action |
| DestinationPort | string | Destination port of related network communications |
| DeviceName | string | Fully qualified domain name (FQDN) of the device |
| IPAddress | string | IP address assigned to the endpoint and used during related network communications |
| ISP | string | Internet service provider (ISP) associated with the endpoint IP address |
| Location | string | City, country/region, or other geographic location associated with the event |
| Port | string | TCP port used during communication |
| Protocol | string | Protocol used during the communication |
| ReportId | string | Unique identifier for the event |
| SourceSystem | string |  |
| TargetAccountDisplayName | string | Display name of the account that the recorded action was applied to |
| TargetAccountUpn | string | User principal name (UPN) of the account that the recorded action was applied to |
| TargetDeviceName | string | Fully qualified domain name (FQDN) of the device that the recorded action was applied to |
| TenantId | string |  |
| TimeGenerated | datetime | Date and time (UTC) when the record was generated |
| Type | string | The name of the table |
