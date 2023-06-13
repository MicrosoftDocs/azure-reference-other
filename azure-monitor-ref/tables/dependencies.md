---
title: Azure Monitor Logs reference - dependencies
description: Reference for dependencies table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/13/2023
---

# dependencies

 

## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| application_Version | string |  |
| _BilledSize | real |  |
| client_Browser | string |  |
| client_City | string |  |
| client_CountryOrRegion | string |  |
| client_IP | string |  |
| client_Model | string |  |
| client_OS | string |  |
| client_StateOrProvince | string |  |
| client_Type | string |  |
| cloud_RoleInstance | string |  |
| cloud_RoleName | string |  |
| customDimensions | dynamic |  |
| customMeasurements | dynamic |  |
| data | string |  |
| duration | real |  |
| id | string |  |
| _IsBillable | string |  |
| itemCount | int |  |
| itemId | string |  |
| name | string |  |
| operation_Id | string |  |
| operation_Name | string |  |
| operation_ParentId | string |  |
| operation_SyntheticSource | string |  |
| performanceBucket | string |  |
| ReferencedType | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| resultCode | string |  |
| sdkVersion | string |  |
| session_Id | string |  |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| success | bool |  |
| target | string |  |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
| type | string |  |
| user_AccountId | string |  |
| user_AuthenticatedId | string |  |
| user_Id | string |  |
