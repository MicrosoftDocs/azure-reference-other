---
title: Example log table queries for ACSBillingUsage
description:  Example queries for ACSBillingUsage log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ACSBillingUsage table


### Get long calls  


Retrive all the calls that lasted longer than an hours.  

```query
ACSBillingUsage
| tolower(UsageType) == "audio" // only look at records that are calls
| extend Length = EndTime - StartTime
| where Length > 1h // return if the call is greater than an hour
```



### Usage breakdown  


Get the total usage for each mode per hour (note that the first and last hours displayed will represent partial data).  

```query
ACSBillingUsage
| summarize Usage=sum(Quantity) by UsageType, bin(TimeGenerated, 1h) // count the number of units for each type of usage, per hour
| render columnchart
```



### Record count breakdown  


Get the unique number of usage records for each mode per hour (note that the first and last hours displayed will represent partial data).  

```query
ACSBillingUsage
| summarize Occurences=dcount(RecordId) by UsageType, bin(TimeGenerated, 1h) // count the number of unique records for each type of usage, per hour
| render columnchart
```



### Participant Phone Numbers  


Lists the phone numbers of the participants in the call. (Phone numbers come from ACSBillingUsage table).  

```query
ACSCallSummary
// Get the calls with CallType as Group
| where CallType == 'Group'
| project CorrelationId, ParticipantId, ParticipantStartTime, ParticipantDuration, EndpointType, CallType, CallStartTime, PstnParticipantCallType
// Join with ACSBillingUsage data on ParticipantId
| join kind=leftouter (ACSBillingUsage
                        | where isnotempty(ParticipantId)
                        | project ParticipantId, UserIdA, UserIdB, StartTime, Quantity)
    on ParticipantId
// Combine with calls of CallType P2P
| union (ACSCallSummary
| where CallType == 'P2P'
| project CorrelationId, ParticipantId, ParticipantStartTime, ParticipantDuration, EndpointType, CallType, CallStartTime, PstnParticipantCallType
// Join with ACSBillingUsage data on CorrelationId
| join kind=leftouter (ACSBillingUsage
                        | where isnotempty(ParticipantId)
                        | project CorrelationId, ParticipantId, UserIdA, UserIdB, StartTime, Quantity)
    on CorrelationId)
| order by CallStartTime, ParticipantStartTime
```

