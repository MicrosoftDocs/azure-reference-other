---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.HealthcareApis/workspaces/dicomservices, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Traffic|**Number of DICOM files processed by import**<br><br>The total number of DICOM files processed by an import. |`ImportsProcessed` |Count |Sum |`Status`, `ResourceName`|PT1M |Yes|