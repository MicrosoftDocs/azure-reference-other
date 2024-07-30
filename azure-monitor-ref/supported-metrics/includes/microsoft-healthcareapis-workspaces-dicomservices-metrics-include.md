---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.HealthcareApis/workspaces/dicomservices, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Traffic|**Number of DICOM files processed by import**<br><br>The total number of DICOM files processed by an import. |`ImportsProcessed` |Count |Sum |`Status`, `ResourceName`|PT1M |Yes|