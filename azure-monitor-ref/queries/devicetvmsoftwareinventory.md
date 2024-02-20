---
title: Example log table queries for DeviceTvmSoftwareInventory
description:  Example queries for DeviceTvmSoftwareInventory log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the DeviceTvmSoftwareInventory table


### Unsupported software titles  


List software titles which are not supported anymore.  

```query
DeviceTvmSoftwareInventory
| where EndOfSupportStatus == 'EOS Software'
| summarize dcount(DeviceId) by SoftwareName
```

