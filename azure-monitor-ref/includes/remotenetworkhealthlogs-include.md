---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/29/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: RemoteNetworkHealthLogs
---


| Column | Type | Description |
|---|---|---|
| BgpRoutesAdvertisedCount | int | Count of BGP routes advertised through tunnel. |
| _BilledSize | real | The record size in bytes |
| CreatedDateTime | datetime | The date and time (UTC) that the event was generated. |
| Description | string | Description and summary of the event. |
| DestinationIp | string | The IP address of the destination. |
| Id | string | A unique identifier for each remoteNetworkHealthEvent. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| ReceivedBytes | long | The number of bytes sent from the destination to the source. |
| RemoteNetworkId | string | A unique identifier for each remoteNetwork site. |
| SentBytes | long | The number of bytes sent from the source to the destination for the connection or session. |
| SourceIp | string | The public IP address. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| Status | string | Remote network status. Possible values are: tunnelDisconnected, tunnelConnected, bgpDisconnected, bgpConnected, remoteNetworkAlive, unknownFutureValue. |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The date and time (UTC) that the event was generated. |
| Type | string | The name of the table |
