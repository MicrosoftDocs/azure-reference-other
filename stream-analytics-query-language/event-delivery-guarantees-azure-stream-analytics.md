---
title: "Event Delivery Guarantees (Azure Stream Analytics) | Microsoft Docs"
description: "Describes the event delivery mechanisms supported in Azure Stream Analytics."
applies_to: 
  - "Azure"
services: "stream-analytics"
author: SnehaGunda
manager: kfile

ms.service: stream-analytics
ms.suite: ""
ms.topic: reference
ms.tgt_pltfrm: ""   
ms.assetid: 3c503b2e-44b6-43bc-9cfa-43bd9430dea1
caps.latest.revision: 6
ms.workload: data-services
ms.date: 05/18/2016
ms.author: sngun
---
# Event Delivery Guarantees (Azure Stream Analytics)
Azure Stream Analytics query language extends SQL syntax to enable complex computations over streams of events. With Stream Analytics there are some concepts related to Event Delivery worth discussing. They are:  
  
*   Exactly once delivery  
*   Duplicate records  
  
Exactly once delivery  
---  
Exactly once delivery guarantee means all input events are processed and only processed once by the streaming system, so the output results are complete, and there is no duplicate output. Azure Stream Analytics guarantees exactly once delivery up to the output adapter that writes the output events.  
  
Duplicate records  
---  
When a Stream Analytics job is running, duplicate records may occasionally be noticed in the output data. These duplicate records expected because Azure Stream Analytics output adapters don’t write the output events transactionally. This 'duplicate record' scenario can result if one of the following conditions occur;  
  
- The Azure instance is upgraded while the job is running  
- The Stream Analytics job is upgraded or an issue occurs with connectivity or reliability to the job output   
- The Azure instance running the job has an outage  
  
The downstream consumer of the output events need to dedupe the events using logical identity of the events. For example, if you are aggregating events by groups in a tumbling window, the logical identity of the event is the groups and the tumbling window’s end time. If you are running a pass through query, you may need to carry a unique id on the event in order to dedupe.  
  
## See Also  
 [Time Management](time-management-azure-stream-analytics.md)  
