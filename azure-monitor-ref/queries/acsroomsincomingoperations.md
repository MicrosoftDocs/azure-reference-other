---
title: Example log table queries for ACSRoomsIncomingOperations
description:  Example queries for ACSRoomsIncomingOperations log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 05/13/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ACSRoomsIncomingOperations table


### Rooms operational errors  


List rooms error ordered by recency.  

```query
ACSRoomsIncomingOperations
| where ResultType == "Failed"
| project TimeGenerated, OperationName, OperationVersion, ResultSignature
| order by TimeGenerated desc
| limit 100
```



### Rooms operation result counts  


For every rooms operation, count the types of returned results.  

```query
ACSRoomsIncomingOperations
| summarize Count = count() by OperationName, OperationVersion, ResultType, ResultSignature
| order by OperationName asc, Count desc
```



### Rooms operation summary  


The average statistics of room properties such as participants count for operation version 2024-04-15.  

```query
ACSRoomsIncomingOperations
// where OperationName == "<operation>" // This can be uncommented and specified to calculate only a single operation's duration percentiles
| where OperationVersion == "2024-04-15" 
| summarize TotalRoomCount = dcount(RoomId),
            AvgAddedParticipantsCount = avg(AddedRoomParticipantsCount),
            AvgRemovedParticipantsCount = avg(RemovedRoomParticipantsCount),
            AvgUpsertedParticipantsCount = avg(UpsertedRoomParticipantsCount),
            AvgRoomLifespan = avg(RoomLifespan),
            SumPstnDialoutEnabled=countif(PstnDialOutEnabled==1)
```

