---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.NetworkAnalytics/DataConnectors, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Data Ingested**<p><p>The volume of data ingested by the pipeline (bytes). |`DataIngested` |Bytes |Total |\<none\>|PT1M |No|
|**Malformed Data**<p><p>The number of files unable to be processed by the pipeline. |`MalformedData` |Count |Total |\<none\>|PT1M |Yes|
|**Malformed Records**<p><p>The number of records unable to be processed by the pipeline. |`MalformedRecords` |Count |Total |\<none\>|PT1M |No|
|**Processed File Count**<p><p>The number of files processed by the data connector. |`ProcessedFileCount` |Count |Total |\<none\>|PT1M |Yes|
|**Running**<p><p>Values greater than 0 indicate that the pipeline is ready to process data. |`Running` |Unspecified |Count |\<none\>|PT1M |Yes|