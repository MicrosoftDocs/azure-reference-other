---
ms.service: azure-monitor
ms.topic: include
ms.date: 06/03/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.DesktopVirtualization/hostpools, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`AgentHealthStatus` |AgentHealthStatus |[WVDAgentHealthStatus](/azure/azure-monitor/reference/tables/wvdagenthealthstatus)<p>Azure Virtual Desktop agent health status.|No|Yes|[Queries](/azure/azure-monitor/reference/queries/wvdagenthealthstatus)|No |
|`AutoscaleEvaluationPooled` |Autoscale logs for pooled host pools |[WVDAutoscaleEvaluationPooled](/azure/azure-monitor/reference/tables/wvdautoscaleevaluationpooled)<p>The results of an Azure Virtual Desktop Autoscale scaling plan evaluation on a hostpool. This includes information on the actions Autoscale took on the sessions hosts, such as starting or deallocating them, and why it took those actions. The column names that start with 'Config' contain the scaling plan configuration values for the current Autoscale schedule phase. If the ResultType column value is 'Failed' then join to the WVDErrors table using the CorrelationId column to get more details. For Autoscale documentation see https://go.microsoft.com/fwlink/?linkid=2169532 .|No|No||Yes |
|`Checkpoint` |Checkpoint |[WVDCheckpoints](/azure/azure-monitor/reference/tables/wvdcheckpoints)<p>Windows Virtual Desktop Checkpoint Activity|No|Yes|[Queries](/azure/azure-monitor/reference/queries/wvdcheckpoints)|No |
|`Connection` |Connection |[WVDConnections](/azure/azure-monitor/reference/tables/wvdconnections)<p>Windows Virtual Desktop Connection Activity.|No|Yes|[Queries](/azure/azure-monitor/reference/queries/wvdconnections)|No |
|`ConnectionGraphicsData` |Connection Graphics Data Logs Preview |[WVDConnectionGraphicsDataPreview](/azure/azure-monitor/reference/tables/wvdconnectiongraphicsdatapreview)<p>Windows Virtual Desktop connection graphics data.|No|No||Yes |
|`Error` |Error |[WVDErrors](/azure/azure-monitor/reference/tables/wvderrors)<p>Windows Virtual Desktop Error Activity|No|Yes|[Queries](/azure/azure-monitor/reference/queries/wvderrors)|No |
|`HostRegistration` |HostRegistration |[WVDHostRegistrations](/azure/azure-monitor/reference/tables/wvdhostregistrations)<p>Windows Virtual Desktop Host Registration Activity|No|Yes||No |
|`Management` |Management |[WVDManagement](/azure/azure-monitor/reference/tables/wvdmanagement)<p>Windows Virtual Desktop Management Activity|No|Yes||No |
|`NetworkData` |Network Data Logs |[WVDConnectionNetworkData](/azure/azure-monitor/reference/tables/wvdconnectionnetworkdata)<p>Windows Virtual Desktop connection network data.|No|Yes|[Queries](/azure/azure-monitor/reference/queries/wvdconnectionnetworkdata)|Yes |
|`SessionHostManagement` |Session Host Management Activity Logs |[WVDSessionHostManagement](/azure/azure-monitor/reference/tables/wvdsessionhostmanagement)<p>Windows Virtual Desktop session host management data.|No|No||Yes |