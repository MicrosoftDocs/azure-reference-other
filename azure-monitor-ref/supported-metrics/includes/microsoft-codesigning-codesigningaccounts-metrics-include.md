---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.CodeSigning/codesigningaccounts, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|audit|**SignCompleted**<br><br>Completed Sign Request |`SignCompleted` |Count |Count, Sum |`CertType`, `Region`, `TenantId`|PT1M |Yes|