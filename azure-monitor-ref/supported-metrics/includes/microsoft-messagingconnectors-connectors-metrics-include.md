---
ms.service: azure-monitor
ms.topic: include
ms.date: 05/20/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.MessagingConnectors/connectors, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Sink Record Read Total By Time**<br><br>Number of records read by the sink connector by time |`SinkRecordReadTotalByTime` |Count |Total |\<none\>|PT1M |Yes|
|**Sink Record Send Total By Time**<br><br>Number of records sent by the sink connector by time |`SinkRecordSendTotalByTime` |Count |Total |\<none\>|PT1M |Yes|
|**Source Record Poll Total By Time**<br><br>Number of records polled by the source connector by time |`SourceRecordPollTotalByTime` |Count |Total |\<none\>|PT1M |Yes|
|**Source Record Write Total**<br><br>Number of records written by the source connector |`SourceRecordWriteTotal` |Count |Maximum, Minimum |\<none\>|PT1M |Yes|
|**Source Record Write Total By Time**<br><br>Number of records written by the source connector by time |`SourceRecordWriteTotalByTime` |Count |Total |\<none\>|PT1M |Yes|
|**Total Errors Logged By Time**<br><br>Number of errors logged by time |`TotalErrorsLoggedByTime` |Count |Total |\<none\>|PT1M |Yes|
|**Total Record Errors By Time**<br><br>Number of records errors by time |`TotalRecordErrorsByTime` |Count |Total |\<none\>|PT1M |Yes|
|**Total Record Failures By Time**<br><br>Number of record failures by time |`TotalRecordFailuresByTime` |Count |Total |\<none\>|PT1M |Yes|
|**Total Records Skipped By Time**<br><br>Number of records skipped by time |`TotalRecordsSkippedByTime` |Count |Total |\<none\>|PT1M |Yes|