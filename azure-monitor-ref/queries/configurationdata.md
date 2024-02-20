---
title: Example log table queries for ConfigurationData
description:  Example queries for ConfigurationData log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ConfigurationData table


### Recent stopped auto services  


Shows most recent services that were set to Auto but reported as being stopped.  

```query
ConfigurationData
| where ConfigDataType == "WindowsServices" and SvcStartupType == "Auto"
| where SvcState == "Stopped"
| summarize arg_max(TimeGenerated, *) by SoftwareName, Computer
```

