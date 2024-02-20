---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: WUDOStatus
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| BWOptPercent28Days | real |   |
| BWOptPercent7Days | real |   |
| BytesFromCDN | long |   |
| BytesFromGroupPeers | long |   |
| BytesFromIntPeers | long |   |
| BytesFromPeers | long |   |
| City | string |   |
| Computer | string |   |
| ComputerID | string |   |
| ContentDownloadMode | int |   |
| ContentType | string |   |
| Country | string |   |
| DOStatusDescription | string |   |
| DownloadMode | string |   |
| DownloadModeSrc | string |   |
| GroupID | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| ISP | string |   |
| LastScan | datetime |   |
| NoPeersCount | long |   |
| OSName | string |   |
| OSVersion | string |   |
| PeerEligibleTransfers | long |   |
| PeeringStatus | string |   |
| PeersCannotConnectCount | long |   |
| PeersSuccessCount | long |   |
| PeersUnknownCount | long |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| TimeGenerated | datetime |   |
| TotalTimeForDownload | string |   |
| TotalTransfers | long |   |
| Type | string | The name of the table |
