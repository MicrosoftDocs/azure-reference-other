---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.HealthcareApis/workspaces/dicomservices, arm
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Number of DICOM files processed by import**<p><p>The total number of DICOM files processed by an import. |`ImportsProcessed` |Count |Sum |`Status`, `ResourceName`|PT1M |Yes|