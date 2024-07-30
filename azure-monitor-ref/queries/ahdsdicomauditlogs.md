---
title: Example log table queries for AHDSDicomAuditLogs
description:  Example queries for AHDSDicomAuditLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AHDSDicomAuditLogs table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### DICOM privileged operations  


Get the count of the privileged operation logs per operation. For example, how many requests have been received to store a DICOM instance.  

```query
AHDSDicomAuditLogs
| summarize Count = count() by OperationName

```

