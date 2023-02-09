---
title: Azure Monitor Logs reference - AVNMNetworkGroupMembershipChange
description: Reference for AVNMNetworkGroupMembershipChange table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 2/10/2023
---

# AVNMNetworkGroupMembershipChange

 Includes changes to network group membership of network resources like a virtual network.

## Categories

- Azure Resources
- Network
- Audit
## Solutions

- LogManagement
## Resource types

- Azure Virtual Network Manager




## Columns

| Column | Type | Description |
| --- | --- | --- |
| CorrelationId | string | The correlation ID associated with the network group membership change operation of network resources. |
| DetailedMessage | string | A descriptive message that can include explanations and resolution steps in the case of failures or warnings. |
| GroupMemberships | dynamic | Details about the Virtual Network's membership of Network Group(s), including the networkgroupId, membership type, and membership details and IDs. |
| Location | string | Region of the Virtual Network. |
| LogLevel | string | Indicates the log level and can include: Info, Warning, Error. |
| Message | string | A brief success or failure message. |
| NetworkResourceIds | dynamic | Virtual Network IDs for which network group membership changed |
| OperationName | string |  Name of the operation that triggered the Virtual Network's addition or removal from a Network Group. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultType | string | Indicates the operation status and can include: Success, Failure. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime |  The date and time the event was generated. |
| Type | string | The name of the table |
