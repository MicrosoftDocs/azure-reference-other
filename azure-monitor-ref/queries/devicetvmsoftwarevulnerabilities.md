---
title: Example log table queries for DeviceTvmSoftwareVulnerabilities
description:  Example queries for DeviceTvmSoftwareVulnerabilities log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the DeviceTvmSoftwareVulnerabilities table


### Devices affected by a specific vulnerability  


List devices affected by a specific vulnerability.  

```query
DeviceTvmSoftwareVulnerabilities
| where CveId == 'CVE-2020-0791'
| limit 100 
```

