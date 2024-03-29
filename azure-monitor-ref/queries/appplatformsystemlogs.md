---
title: Example log table queries for AppPlatformSystemLogs
description:  Example queries for AppPlatformSystemLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AppPlatformSystemLogs table


### Show the config server logs  


View config server logs of level warn and error for Basic and Standard tiers.  

```query
AppPlatformSystemLogs 
| where LogType == "ConfigServer" and Level in ("WARN", "ERROR")
| project TimeGenerated , Level , ServiceName , Thread , Stack , Log , _ResourceId 
| limit 100
```



### Show the service registry logs  


View service registry logs of level warn and error for all tiers.  

```query
AppPlatformSystemLogs 
| where LogType == "ServiceRegistry" and Level in ("WARN", "ERROR")
| project TimeGenerated , Level , ServiceName , Thread , Stack , Log , _ResourceId 
| limit 100
```



### Show the Spring Cloud Gateway logs  


View Spring Cloud Gateway logs for Enterprise tiers.  

```query
AppPlatformSystemLogs 
| where LogType == "SpringCloudGateway"
| project TimeGenerated , ServiceName , Log , _ResourceId 
| limit 100
```



### Show the API portal logs  


View API portal logs for Enterprise tiers.  

```query
AppPlatformSystemLogs 
| where LogType == "ApiPortal"
| project TimeGenerated , ServiceName , Log , _ResourceId 
| limit 100
```



### Show the Application Configuration Service logs  


View Application Configuration Service logs for Enterprise tiers.  

```query
AppPlatformSystemLogs 
| where LogType == "ApplicationConfigurationService"
| project TimeGenerated , ServiceName , Log , _ResourceId 
| limit 100
```



### Show the Spring Cloud Gateway operator logs  


View Spring Cloud Gateway operator logs for Enterprise tiers.  

```query
AppPlatformSystemLogs 
| where LogType == "SpringCloudGatewayOperator"
| project TimeGenerated , ServiceName , Log , _ResourceId 
| limit 100
```

