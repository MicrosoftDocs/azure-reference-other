---
title: Example log table queries for AZFWFatFlow
description:  Example queries for AZFWFatFlow log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AZFWFatFlow table


### Azure Firewall Top Flow Logs  


Identify top flows across Azure Firewall instances. Log contains flow information, date transmission rate (in Megabits per second units) and the time period when the flows were recorded.  

```query
// Get the fatflows from past 1000 samples with rate atleast 5 mbps
AZFWFatFlow
| take 1000
| order by TimeGenerated desc
| where FlowRate > 5

```

