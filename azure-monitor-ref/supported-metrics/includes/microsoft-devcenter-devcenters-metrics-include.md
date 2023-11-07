---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/29/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.DevCenter/devcenters, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Failed creations**<p><p>Count of dev boxes which failed to create. |`DevBoxCreationFailed` |Count |Count |`ProjectId`, `ErrorCode`|PT1M |Yes|
|**Successful creations**<p><p>Count of dev boxes which were created successfully. |`DevBoxCreationSucceeded` |Count |Count |`ProjectId`|PT1M |Yes|
|**Failed creations**<p><p>Count of failed dev box definitions which can be filtered by error code. |`DevBoxDefinitionCreationFailed` |Count |Count |`ErrorDetails`|PT1M |Yes|
|**Image Validation Duration**<p><p>Time taken for validating created device images. |`ImageValidationDuration` |Seconds |Average, Maximum, Minimum |\<none\>|PT1M |Yes|