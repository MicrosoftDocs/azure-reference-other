---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.MobileNetwork/mobilenetworks/sites, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Correlation|**Correlated Downlink Volume**<br><br>This metric is created by correlating successful RAN Received Volme and packet core received Transmitted Volume on N3 interface |`DownlinkVolume` |Percent |Average |`RANIdentifier`|PT1M |No|
|Correlation|**Correlated Successful Established Radio Connections**<br><br>This metric is created by correlating successful RAN radio connections established and packet core Initial Ue Message |`RadioConnectionsEstablished` |Percent |Average |\<none\>|PT1M |No|
|Correlation|**Correlated Successful Handovers**<br><br>This metric is created by correlating successful RAN Connection Handover and packet core Handovers |`SuccessfulHandovers` |Percent |Average |\<none\>|PT1M |No|
|Correlation|**Correlated Uplink Volume**<br><br>This metric is created by correlating successful RAN Transmitted Volme and packet core received Received Volume on N3 interface |`UplinkVolume` |Percent |Average |`RANIdentifier`|PT1M |No|