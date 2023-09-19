---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.NetworkAnalytics/DataConnectors, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Data Ingested<p><p>The volume of data ingested by the pipeline (bytes). |`DataIngested` |Bytes |Total |No Dimensions|PT1M |No|
|Malformed Data<p><p>The number of files unable to be processed by the pipeline. |`MalformedData` |Count |Total |No Dimensions|PT1M |Yes|
|Malformed Records<p><p>The number of records unable to be processed by the pipeline. |`MalformedRecords` |Count |Total |No Dimensions|PT1M |No|
|Processed File Count<p><p>The number of files processed by the data connector. |`ProcessedFileCount` |Count |Total |No Dimensions|PT1M |Yes|
|Running<p><p>Values greater than 0 indicate that the pipeline is ready to process data. |`Running` |Unspecified |Count |No Dimensions|PT1M |Yes|