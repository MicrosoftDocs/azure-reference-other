---
title: Supported metrics - Microsoft.Network/virtualNetworks
description: Reference for Microsoft.Network/virtualNetworks metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 09/19/2023
ms.custom: Microsoft.Network/virtualNetworks, arm
---




# Supported metrics for Microsoft.Network/virtualNetworks


The following table lists the metrics available for the Microsoft.Network/virtualNetworks resource type.

  
    
**Table headings**
  
**Metric** - The metric display name as it appears in the Azure portal.  
**Name** - Metric name as referred to in the REST API.  
**Unit** - Unit of measure.  
**Aggregation** - The default aggregation type. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available for the metric.  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  
**Time Grains** - Intervals at which the metric is sampled. For example, `PT1M` indicates that the metric is sampled every minute, `PT30M` every 30 minutes, `PT1H` every hour, and so on.  

> [!NOTE] 
> The PingMeshAverageRoundtripMs and PingMeshProbesFailedPercent metrics are legacy and may appear in Azure Portal but are not available.


  
  
[!INCLUDE [Microsoft.Network/virtualNetworks](./includes/Microsoft-Network-virtualNetworks-metrics-include.md)]
      
