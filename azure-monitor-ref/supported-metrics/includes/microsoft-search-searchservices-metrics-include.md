---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Search/searchServices, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Document processed count**<p><p>Number of documents processed |`DocumentsProcessedCount` |Count |Total, Count |`DataSourceName`, `Failed`, `IndexerName`, `IndexName`, `SkillsetName`|PT1M |Yes|
|**Search Latency**<p><p>Average search latency for the search service |`SearchLatency` |Seconds |Average |\<none\>|PT1M |Yes|
|**Search queries per second**<p><p>Search queries per second for the search service |`SearchQueriesPerSecond` |CountPerSecond |Average |\<none\>|PT1M |Yes|
|**Skill execution invocation count**<p><p>Number of skill executions |`SkillExecutionCount` |Count |Total, Count |`DataSourceName`, `Failed`, `IndexerName`, `SkillName`, `SkillsetName`, `SkillType`|PT1M |Yes|
|**Throttled search queries percentage**<p><p>Percentage of search queries that were throttled for the search service |`ThrottledSearchQueriesPercentage` |Percent |Average |\<none\>|PT1M |Yes|