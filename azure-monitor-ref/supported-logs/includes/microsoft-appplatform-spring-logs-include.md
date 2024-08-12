---
ms.service: azure-monitor
ms.topic: include
ms.date: 08/12/2024
ms.author: orens
author: osalzberg
ms.custom: Microsoft.AppPlatform/spring, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`ApplicationConsole` |Application Console |[AppPlatformLogsforSpring](/azure/azure-monitor/reference/tables/appplatformlogsforspring)<p>App Platform Logs for Spring.|No|Yes||No |
|`BuildLogs` |Build Logs |[AppPlatformBuildLogs](/azure/azure-monitor/reference/tables/appplatformbuildlogs)<p>Azure Spring Cloud build logs of user source codes.|No|No||Yes |
|`ContainerEventLogs` |Container Event Logs |[AppPlatformContainerEventLogs](/azure/azure-monitor/reference/tables/appplatformcontainereventlogs)<p>Azure Spring Cloud container event logs of user applications.|No|No||Yes |
|`IngressLogs` |Ingress Logs |[AppPlatformIngressLogs](/azure/azure-monitor/reference/tables/appplatformingresslogs)<p>Azure Spring Cloud ingress logs, currently it is nginx access logs.|No|Yes||Yes |
|`SystemLogs` |System Logs |[AppPlatformSystemLogs](/azure/azure-monitor/reference/tables/appplatformsystemlogs)<p>Azure Spring Cloud System Logs.|No|Yes||No |