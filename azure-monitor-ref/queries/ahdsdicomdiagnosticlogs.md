---
title: Example log table queries for AHDSDicomDiagnosticLogs
description:  Example queries for AHDSDicomDiagnosticLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AHDSDicomDiagnosticLogs table


### Log count per log starting with Dicom100 error code and CorrelationId  


Get the count of logs starting with Dicom100 error emitted from Dicom service per CorrelationId. The result contains count by CorrelationId.  

```query
AHDSDicomDiagnosticLogs
| where Message startswith "DICOM100:"
| summarize Count = count() by CorrelationId

```

