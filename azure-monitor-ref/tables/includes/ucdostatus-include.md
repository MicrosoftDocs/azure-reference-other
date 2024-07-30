---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: UCDOStatus
---


| Column | Type | Description |
|---|---|---|
| AzureADDeviceId | string | A GUID corresponding to the AAD tenant to which the device belongs. |
| AzureADTenantId | string | A GUID corresponding to this device's AAD device ID. |
| _BilledSize | real | The record size in bytes |
| BWOptPercent28Days | real | Bandwidth optimization (as a percentage of savings of total bandwidth otherwise incurred) as a result of using delivery optimization for this device, computed on a rolling 28-day basis. |
| BWOptPercent7Days | real | Bandwidth optimization (as a percentage of savings of total bandwidth otherwise incurred) as a result of using delivery optimization for this device, computed on a rolling 7-day basis. |
| BytesFromCache | long | Total number of bytes downloaded from cache. |
| BytesFromCDN | long | Total number of bytes downloaded from a CDN versus a peer. This counts against bandwidth optimization. |
| BytesFromGroupPeers | long | Total number of bytes downloaded from group peers. |
| BytesFromIntPeers | long | Total number of bytes downloaded from internet peers. |
| BytesFromPeers | long | Total number of bytes downloaded from peers. |
| City | string | Approximate city device was in while downloading content, based on IP address. |
| ContentDownloadMode | int | Device's delivery optimization download mode that was used for this content. |
| ContentType | string | The type of content being downloaded. |
| Country | string | Approximate country device was in while downloading content, based on IP address. |
| DeviceName | string | User or organization-provided device name. If this appears as '#', then you may need to configure devices to send device name. |
| DOStatusDescription | string | A short description of DO's status, if any. |
| DownloadMode | string | Device's delivery optimization download mode as configured on the device. |
| DownloadModeSrc | string | The source of the download mode configuration. |
| GlobalDeviceId | string | Microsoft global device identifier. This is a identifier used by Microsoft internally. |
| GroupID | string | The delivery optimization group ID. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| ISP | string | The internet service provider estimation. |
| LastCensusSeenTime | datetime | A DateTime corresponding to the last time the device sent data to Microsoft. Indicates freshness of any fields of this record. |
| NoPeersCount | long | The count of peers this device interacted with. |
| OSVersion | string | The version of Windows 10. This typically is of the format of the year of the version's release, following the month. In this example, `1909` corresponds to 2019-09 (September). This maps to the `Major` portion of OSBuild. |
| PeerEligibleTransfers | long | Total count of eligible transfers by peers. |
| PeeringStatus | string | The DO peering status. |
| PeersCannotConnectCount | long | The count of peers this device was unable to connect to. |
| PeersSuccessCount | long | The count of peers this device successfully connected to. |
| PeersUnknownCount | long | The count of peers for which there is an unknown relation. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Time at which this event was generated. |
| TotalTimeForDownload | string | The total time it took to download the content. |
| TotalTransfers | long | The total count of data transfers to download this content. |
| Type | string | The name of the table |
