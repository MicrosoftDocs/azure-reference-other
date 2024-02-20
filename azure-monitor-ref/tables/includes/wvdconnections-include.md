---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: WVDConnections
---


| Column | Type | Description |
|---|---|---|
| AadTenantId | string | The AAD tenant Id of the user. |
| _BilledSize | real | The record size in bytes |
| ClientOS | string | The OS of the client that is connecting (if available). |
| ClientSideIPAddress | string | The remote IP address from the client side. |
| ClientType | string | The type of the client that is connecting (if available). |
| ClientVersion | string | The version of the client that is connecting (if available). |
| ConnectionType | string | The type of connection - either RAIL (RemoteApp Integrated Locally) or Desktop. |
| CorrelationId | string | The activity Id. |
| GatewayRegion | string | The region of the WVD Gateway for the server side user connection. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| IsClientPrivateLink | string | True if the client side of this connection used a private link endpoint during orchestration. |
| IsSessionHostPrivateLink | string | True if the session host side of this connection used a private link endpoint during orchestration. |
| PredecessorConnectionId | string | The predecessor Correlation Id of the connection, if the current connection is an auto-reconnect. |
| ResourceAlias | string | The alias of the app that the user attempted to connect to. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SessionHostAgentVersion | string | The version of the WVD Agent running on the machine where the user connection was orchestrated. |
| SessionHostAzureVmId | string | The Azure VM Id of the machine where the user connection was orchestrated. |
| SessionHostIPAddress | string | The IP address of the machine where the user connection was orchestrated. |
| SessionHostJoinType | string | The type of the domain join for the Session Host - either DomainJoined, HybridAzureADJoined or AzureADJoined. |
| SessionHostName | string | The FQDN of the machine where the user connection was orchestrated. |
| SessionHostOSDescription | string | The OS SKU description of the machine where the user connection was orchestrated. |
| SessionHostOSVersion | string | The OS version of the machine where the user connection was orchestrated. |
| SessionHostPoolType | string | The type of session host pool - either SharedDesktop or PersonalDesktop. |
| SessionHostSessionId | string | The Session Id of WVD RDP Stack running on the machine where the user connection was orchestrated. |
| SessionHostSxSStackVersion | string | The version of the WVD RDP Stack running on the machine where the user connection was orchestrated. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| State | string | The state of the connection. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of the event. |
| Type | string | The name of the table |
| UdpUse | string | Indicates whether WVD RDP Stack uses UDP protocol on current user connection. |
| UserName | string | The user who initiated the connection. |
