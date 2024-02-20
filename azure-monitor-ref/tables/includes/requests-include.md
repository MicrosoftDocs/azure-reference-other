---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: requests
---


| Column | Type | Description |
|---|---|---|
| application_Version | string |   |
| _BilledSize | real | The record size in bytes |
| client_Browser | string |   |
| client_City | string |   |
| client_CountryOrRegion | string |   |
| client_IP | string |   |
| client_Model | string |   |
| client_OS | string |   |
| client_StateOrProvince | string |   |
| client_Type | string |   |
| cloud_RoleInstance | string |   |
| cloud_RoleName | string |   |
| customDimensions | dynamic |   |
| customMeasurements | dynamic |   |
| duration | real |   |
| id | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| itemCount | int |   |
| itemId | string |   |
| name | string |   |
| operation_Id | string |   |
| operation_Name | string |   |
| operation_ParentId | string |   |
| operation_SyntheticSource | string |   |
| performanceBucket | string |   |
| ReferencedType | string |   |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| resultCode | string |   |
| sdkVersion | string |   |
| session_Id | string |   |
| source | string |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| success | bool |   |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
| url | string |   |
| user_AccountId | string |   |
| user_AuthenticatedId | string |   |
| user_Id | string |   |
