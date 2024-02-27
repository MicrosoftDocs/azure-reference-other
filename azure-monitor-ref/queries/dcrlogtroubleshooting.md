---
title: Example log table queries for DCRLogTroubleshooting
description:  Example queries for DCRLogTroubleshooting log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/26/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the DCRLogTroubleshooting table


### Verbose ingestion and transformation errors from data collection rules  


Retrieves verbose logs indicating ingestion and transformation failures during logs ingestion using data collection rules.  

```query
// This query helps list the most recent 10 logs for verbose failures during log ingestion/transformation. 
DCRLogTroubleshooting
//| where OperationName == "Ingestion" // Uncomment this line to see Ingestion errors
//| where OperationName =="Transformation" // Uncomment this line to see Transformation errors
| sort by TimeGenerated desc
| limit 10

```

