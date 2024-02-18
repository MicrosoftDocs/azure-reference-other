---
title: Example log table queries for UCDOStatus
description:  Example queries for UCDOStatus log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the UCDOStatus table


### Device configuration  


Get the count of device by download mode in DO status.  

```query
UCDOStatus| 
summarize count() by DownloadMode
```

