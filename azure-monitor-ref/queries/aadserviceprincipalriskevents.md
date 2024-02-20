---
title: Example log table queries for AADServicePrincipalRiskEvents
description:  Example queries for AADServicePrincipalRiskEvents log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AADServicePrincipalRiskEvents table


### Active service principal risk detections  


Gets a list of active service principal risk detections.  

```query
AADServicePrincipalRiskEvents
| summarize arg_max(LastUpdatedDateTime, *) by RequestId, ServicePrincipalId
| where RiskState == "atRisk"
```

