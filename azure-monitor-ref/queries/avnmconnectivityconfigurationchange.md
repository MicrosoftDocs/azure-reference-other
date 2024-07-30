---
title: Example log table queries for AVNMConnectivityConfigurationChange
description:  Example queries for AVNMConnectivityConfigurationChange log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AVNMConnectivityConfigurationChange table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Recent connectivity configuration changes  


List 10 most recent connectivity configuration changes.  

```query
AVNMConnectivityConfigurationChange
| top 10 by TimeGenerated desc
| project TimeGenerated, NetworkResourceIds, AppliedConnectivityConfigurations, ResultType
```



### Recent failed connectivity configuration changes  


List 100 most recent failed connectivity configuration changes.  

```query
AVNMConnectivityConfigurationChange
| where ResultType != "Success"
| sort by TimeGenerated desc
| take 100

```

