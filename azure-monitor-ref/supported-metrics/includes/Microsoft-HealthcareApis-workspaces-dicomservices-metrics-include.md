---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.HealthcareApis/workspaces/dicomservices, arm
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Number of DICOM files processed by import<p><p>The total number of DICOM files processed by an import. |`ImportsProcessed` |Count |Sum |Status, ResourceName|PT1M |Yes|