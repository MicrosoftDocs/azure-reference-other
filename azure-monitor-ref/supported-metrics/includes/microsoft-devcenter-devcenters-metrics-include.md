---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.DevCenter/devcenters, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|DevBox Creations|**Failed creations**<p><p>Count of dev boxes which failed to create. |`DevBoxCreationFailed` |Count |Count |`ProjectId`, `ErrorCode`|PT1M |Yes|
|DevBox Creations|**Successful creations**<p><p>Count of dev boxes which were created successfully. |`DevBoxCreationSucceeded` |Count |Count |`ProjectId`|PT1M |Yes|
|DevBox Definition Creations|**Failed creations**<p><p>Count of failed dev box definitions which can be filtered by error code. |`DevBoxDefinitionCreationFailed` |Count |Count |`ErrorDetails`|PT1M |Yes|
|Performance|**Image Validation Duration**<p><p>Time taken for validating created device images. |`ImageValidationDuration` |Seconds |Average, Maximum, Minimum |\<none\>|PT1M |Yes|