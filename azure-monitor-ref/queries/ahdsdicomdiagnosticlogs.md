---
title: Example log table queries for AHDSDicomDiagnosticLogs
description:  Example queries for AHDSDicomDiagnosticLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AHDSDicomDiagnosticLogs table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Log count per log starting with Dicom100 error code and CorrelationId  


Get the count of logs starting with Dicom100 error emitted from Dicom service per CorrelationId. The result contains count by CorrelationId.  

```query
AHDSDicomDiagnosticLogs
| where Message startswith "DICOM100:"
| summarize Count = count() by CorrelationId

```

