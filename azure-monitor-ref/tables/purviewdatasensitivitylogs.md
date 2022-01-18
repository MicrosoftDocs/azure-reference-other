---
title: Azure Monitor Logs reference - PurviewDataSensitivityLogs
description: Reference for PurviewDataSensitivityLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 1/13/2022
---

# PurviewDataSensitivityLogs

 Data Sensitivity information for assets scanned using Purview.

## Categories

- Security
- Azure Resources
## Solutions

- LogManagement
## Resource types

- Microsoft Defender for cloud
- Microsoft.Purview/accounts




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ActivityType | string | The type of data sensitivity event. |
| AssetCreationTime | datetime | Time at which the asset was created. |
| AssetLastScanTime | datetime | Time at which the asset was last scanned. |
| AssetModifiedTime | datetime | Time at which the asset was last modified. |
| AssetName | string | Name of the asset scanned. |
| AssetPath | string | Path of the asset scanned. |
| AssetType | string | Type of asset that was scanned. |
| Classification | dynamic | List of classifications found. |
| ClassificationDetails | dynamic | List of classification details: ID, name, count, uniquecount, confidence. |
| ClassificationTrigger | string | The trigger for the classification event. |
| FileExtension | string | File extension of the asset scanned. |
| FileSize | long | File size of the asset scanned. |
| PurviewAccountName | string | Name of the Purview account. |
| PurviewRegion | string | Region of the Purview account. |
| PurviewTenantId | string | Tenant ID associated with the Purview account. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SensitivityLabel | dynamic | Names for the labels found. |
| SensitivityLabelDetails | dynamic | List of label details: ID, name, order. |
| SensitivityLabelTrigger | string | The trigger for the sensitivity label event. |
| SourceCollectionName | string | Name of the data source collection name in Purview. |
| SourceName | string | Name of the data source scanned. |
| SourcePath | string | Resource Path of the data source. Ex: ARM path for Azure resources and ARN for AWS resources |
| SourceRegion | string | The location of the data source. |
| SourceScanId | string | The associated Purview scan ID for the source. |
| SourceSubscriptionId | string | Subscription ID associated with the data source. |
| SourceSystem | string |  |
| SourceType | string | Type of data source scanned. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Time (UTC) when the log was generated. |
| Type | string | The name of the table |
