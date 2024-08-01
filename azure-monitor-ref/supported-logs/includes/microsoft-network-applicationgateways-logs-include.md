---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: Microsoft.Network/applicationgateways, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`ApplicationGatewayAccessLog` |Application Gateway Access Log |[AGWAccessLogs](/azure/azure-monitor/reference/tables/agwaccesslogs)<p>Contains all the log to view Application Gateway access patterns and analyze important information. This includes the caller's IP, requested URL, response latency, return code, and bytes in and out.|Yes|No||No |
|`ApplicationGatewayFirewallLog` |Application Gateway Firewall Log |[AGWFirewallLogs](/azure/azure-monitor/reference/tables/agwfirewalllogs)<p>Contains all the logs to view the requests that are logged through either detection or prevention mode of an application gateway that is configured with the web application firewall.|Yes|No||No |
|`ApplicationGatewayPerformanceLog` |Application Gateway Performance Log |[AGWPerformanceLogs](/azure/azure-monitor/reference/tables/agwperformancelogs)<p>Contains all the logs to view how Application Gateway instances are performing. This log captures performance information for each instance, including total requests served, throughput in bytes, total requests served, failed request count, and healthy and unhealthy backend instance count.The Performance log is available only for the v1 SKU.|Yes|No||No |