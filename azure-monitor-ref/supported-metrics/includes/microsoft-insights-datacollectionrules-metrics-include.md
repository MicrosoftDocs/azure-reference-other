---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Insights/datacollectionrules, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Logs Ingestion Requests per Minute**<p><p>Number of requests received via Log Ingestion API or from the agent |`ApiCallReceived_Count` |Count |Count |`InputStreamId`, `ResponseCode`|PT1M |Yes|
|**Logs Ingestion Bytes per Minute**<p><p>Number of bytes received via Log Ingestion API or from the agent |`BytesReceived_Count` |Bytes |Total, Average, Minimum, Maximum |`InputStreamId`|PT1M |Yes|
|**Logs Transformation Rows Dropped per Minute**<p><p>Number of rows dropped while running transformation. |`RowsDropped_Count` |Count |Total, Average, Minimum, Maximum |`InputStreamId`|PT1M |Yes|
|**Logs Transformation Rows Received per Minute**<p><p>Total number of rows recevied for transformation. |`RowsReceived_Count` |Count |Total, Average, Minimum, Maximum |`InputStreamId`|PT1M |Yes|
|**Logs Transformation Errors per Minute**<p><p>The number of times when execution of KQL transformation resulted in an error, e.g. KQL syntax error or going over a service limit. |`TransformationErrors_Count` |Count |Count |`InputStreamId`, `ErrorType`|PT1M |Yes|
|**Logs Transformation Duration per Minute**<p><p>Total time taken to transform given set of records, measured in milliseconds. |`TransformationRuntime_DurationMs` |MilliSeconds |Average, Minimum, Maximum |`InputStreamId`|PT1M |Yes|