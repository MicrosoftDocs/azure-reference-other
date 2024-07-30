---
title: Example log table queries for ACICollaborationAudit
description:  Example queries for ACICollaborationAudit log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ACICollaborationAudit table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### How many times a resource was granted grants per pipeline run?  


Return the number of times access was granted for resources during pipeline run. Grouped by the type of grant: Entitlement (by participant in production mode), Referenced (by participant in test mode) or Owner (by the owner of the resource).  

```query
//=================================================================================================================================================================
// summarize by CorrelationId groups audits by pipeline run. For more details about summarize see: https://docs.microsoft.com/en-us/azure/data-explorer/kusto/query/summarizeoperator
ACICollaborationAudit
| summarize PipelineExecutedOn=max(TimeGenerated), ResourceAccessGrantCount=count(), EntitlementResult=array_strcat(make_set(EntitlementResult), ',') by CorrelationId, GrantType, TargetResourceId
| project-away CorrelationId
| order by PipelineExecutedOn desc, TargetResourceId asc
| top 100 by PipelineExecutedOn;

```



### What entitlements was granted to my resource?  


Find entitlements that was granted to CI resources. Can be used to query a specific resource.  

```query
//==============================================================================================
// For specific results, insert values in the let statements and uncomment the where filters within the query
// let partialResourceId = "<Full or Partial resource name (DataAsset, DataSet or Script) to look for (e.g. "dataassets/e2etest2020qqigqeqp">");
ACICollaborationAudit
| where GrantType == 'Entitlement'
//| where TargetResourceId has partialResourceId
| extend ShortOperationName=tostring(array_slice(split(OperationName, '/'), -1, -1)[0])
| summarize TimeGenerated=max(TimeGenerated), EntitlementResult=array_strcat(make_set(EntitlementResult), ','), 
            GrantSource=any(GrantSource), GrantSourceType=any(GrantSourceType),
            TargetResourceId=any(TargetResourceId), TargetResourceType=any(TargetResourceType), ParticipantName=any(ParticipantName),
            OperationName=any(ShortOperationName)
    by GrantCorrelationId
| project-away GrantCorrelationId
| order by TimeGenerated desc
| limit 100;

```



### What resources was granted accessed by an entitlement?  


Find CI resources that was entitled for access. Can be used to query a specific entitlement.  

```query
//============================================================================================
// For specific results, insert values in the let statements and uncomment the where filters within the query
// let entitlementOrContract = "<Full or Partial entitlement (or contract) name to look for (e.g. "proposals/e2etest2020qytcbkar","entitlements/e2etest2020nzutiqca">");
ACICollaborationAudit 
| where GrantType == 'Entitlement'
//| where GrantSource has entitlementOrContract
| extend ShortOperationName=tostring(array_slice(split(OperationName, '/'), -1, -1)[0])
| summarize TimeGenerated=max(TimeGenerated), EntitlementResult=array_strcat(make_set(EntitlementResult), ','),
            TargetResourceId=any(TargetResourceId), TargetResourceType=any(TargetResourceType), 
            ParticipantName=any(ParticipantName), GrantSource=any(GrantSource), GrantSourceType=any(GrantSourceType),
            OperationName=any(ShortOperationName)
    by GrantCorrelationId
| project-away GrantCorrelationId
| order by TimeGenerated desc
| limit 100;

```



### Which participants was granted accessed to my resource?  


Find participants that was granted access to CI resources. Can be used to query a specific resource.  

```query
//=====================================================================================================
// For specific results, insert values in the let statements and uncomment the where filters within the query
// let partialParticipantName = "<Full or Partial participant (or tenant) name to look for (e.g. "propmtion.dept@contoso">");
ACICollaborationAudit 
| where GrantType == 'Entitlement'
//| where ParticipantName contains partialParticipantName
| extend ShortOperationName=tostring(array_slice(split(OperationName, '/'), -1, -1)[0])
| summarize TimeGenerated=max(TimeGenerated), EntitlementResult=array_strcat(make_set(EntitlementResult), ','),
            TargetResourceId=any(TargetResourceId), TargetResourceType=any(TargetResourceType), 
            GrantSource=any(GrantSource), GrantSourceType=any(GrantSourceType),
            OperationName=any(ShortOperationName), ParticipantName=any(ParticipantName)
    by GrantCorrelationId
| project-away GrantCorrelationId
| order by TimeGenerated desc
| limit 100;

```

