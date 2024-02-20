---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Synapse/workspaces, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`BuiltinSqlReqsEnded` |Built-in Sql Pool Requests Ended |[SynapseBuiltinSqlPoolRequestsEnded](/azure/azure-monitor/reference/tables/synapsebuiltinsqlpoolrequestsended)<p>Ended Azure Synapse built-in serverless SQL requests.|No|Yes||No |
|`GatewayApiRequests` |Synapse Gateway Api Requests |[SynapseGatewayApiRequests](/azure/azure-monitor/reference/tables/synapsegatewayapirequests)<p>Azure Synapse gateway API requests.|No|Yes||No |
|`IntegrationActivityRuns` |Integration Activity Runs |[SynapseIntegrationActivityRuns](/azure/azure-monitor/reference/tables/synapseintegrationactivityruns)<p>Logs for Synapse integration activity runs.|No|Yes||Yes |
|`IntegrationPipelineRuns` |Integration Pipeline Runs |[SynapseIntegrationPipelineRuns](/azure/azure-monitor/reference/tables/synapseintegrationpipelineruns)<p>Logs for Synapse integration pipeline runs.|No|Yes||Yes |
|`IntegrationTriggerRuns` |Integration Trigger Runs |[SynapseIntegrationTriggerRuns](/azure/azure-monitor/reference/tables/synapseintegrationtriggerruns)<p>Logs for Synapse integration trigger runs.|No|Yes||Yes |
|`SQLSecurityAuditEvents` |SQL Security Audit Event |[SQLSecurityAuditEvents](/azure/azure-monitor/reference/tables/sqlsecurityauditevents)<p>Azure Synapse SQL Audit Log.|No|Yes||No |
|`SynapseLinkEvent` |Synapse Link Event |[SynapseLinkEvent](/azure/azure-monitor/reference/tables/synapselinkevent)<p>Information about Synapse Link, including Link status and Link table status.|No|No|[Queries](../../queries/synapselinkevent.md)|Yes |
|`SynapseRbacOperations` |Synapse RBAC Operations |[SynapseRbacOperations](/azure/azure-monitor/reference/tables/synapserbacoperations)<p>Azure Synapse role-based access control (SRBAC) operations.|No|Yes||No |