---
title: Example log table queries for AHDSDicomAuditLogs
description:  Example queries for AHDSDicomAuditLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AHDSDicomAuditLogs table


### DICOM privileged operations  


Get the count of the privileged operation logs per operation. For example, how many requests have been received to store a DICOM instance.  

```query
AHDSDicomAuditLogs
| summarize Count = count() by OperationName

```

