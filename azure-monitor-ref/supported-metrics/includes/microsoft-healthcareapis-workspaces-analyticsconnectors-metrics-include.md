---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.HealthcareApis/workspaces/analyticsconnectors, arm
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Analytics Connector Health Status<p><p>The health status of analytics connector |`AnalyticsConnectorHealthStatus` |Count |Sum |Operation, Component|PT1M |Yes|
|Analytics Connector Process Latency<p><p>The response latency of the service. |`AnalyticsConnectorResourceLatency` |Milliseconds |Average |No Dimensions|PT1M |Yes|
|Analytics Connector Successful Data Size<p><p>The size of data successfully processed by the analytics connector |`AnalyticsConnectorSuccessfulDataSize` |Count |Sum |No Dimensions|PT1M |Yes|
|Analytics Connector Successful Resource Count<p><p>The amount of data successfully processed by the analytics connector |`AnalyticsConnectorSuccessfulResourceCount` |Count |Sum |No Dimensions|PT1M |Yes|
|Analytics Connector Total Error Count<p><p>The total number of errors logged by the analytics connector |`AnalyticsConnectorTotalError` |Count |Sum |ErrorType, Operation|PT1M |Yes|