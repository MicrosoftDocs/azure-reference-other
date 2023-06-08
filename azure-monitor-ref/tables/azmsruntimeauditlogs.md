---
title: Azure Monitor Logs reference - AZMSRunTimeAuditLogs
description: Reference for AZMSRunTimeAuditLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
---

# AZMSRunTimeAuditLogs

 Captures aggregated diagnostic information for various data plane access operations (such as send or receive messages) in Azure Event Hubs and Azure Service Bus. Runtime audit logs are currently available only in premium tier.

## Categories

- Audit
## Solutions

- LogManagement
## Resource types

- Service Bus




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ActivityId | string | A randomly generated UUID that ensures uniqueness for the audit activity. |
| ActivityName | string | Runtime operation name. |
| AuthKey | string | Azure Active Directory application ID or SAS policy name that's used to authenticate to a resource. |
| AuthType | string | Type of authentication (Azure Active Directory or SAS Policy). |
| _BilledSize | real |  |
| ClientIp | string | IP address of the client application. |
| Count | int | Total number of operations performed during the aggregated period of 1 minute. |
| _IsBillable | string |  |
| NetworkType | string | Type of the network access: Public or Private. |
| Properties | dynamic | Metadata that are specific to the data plane operation. |
| Protocol | string | Type of the protocol associated with the operation. |
| Provider | string | Event provider name. Possible values: eventhub, relay, and servicebus. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| Status | string | Status of the activity (success or failure). |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The event generation time (UTC). |
| Type | string | The name of the table |
