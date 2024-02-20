---
title: Example log table queries for ACSCallAutomationMediaSummary
description:  Example queries for ACSCallAutomationMediaSummary log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ACSCallAutomationMediaSummary table


### Loop play success rate  


Calculates the number of success and failures of the play operation when played in loop or not.  

```query
ACSCallAutomationMediaSummary
| where OperationName == "Play"
| summarize playedInLoopCount=count() by PlayInLoop, ResultType
```



### Play to participant success rate  


Calculates the number of success and failures of the play operation when played to a participant or to all.  

```query
ACSCallAutomationMediaSummary
| where OperationName == "Play"
| summarize playedToCount=count() by PlayToParticipant, ResultType
```



### Recognize success rate  


Calculates the number of success and failures of the recognize operation.  

```query
ACSCallAutomationMediaSummary
| where OperationName == "Recognize"
| summarize recognizeCount=count() by ResultType
```



### Success rate by sub operation name  


Calculates the number of success and failures of the recognize operation based on its sub operation name.  

```query
ACSCallAutomationIncomingOperations
| join ACSCallAutomationMediaSummary on OperationId
| where OperationName == "Recognize"
| summarize recognizeCount=count() by SubOperationName, ResultType1
| project SubOperationName, EventResultType = ResultType1, recognizeCount
```

