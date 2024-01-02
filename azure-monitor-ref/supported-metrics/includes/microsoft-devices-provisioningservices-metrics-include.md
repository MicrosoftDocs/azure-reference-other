---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Devices/provisioningServices, arm
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Attestation attempts**<p><p>Number of device attestations attempted |`AttestationAttempts` |Count |Total |`ProvisioningServiceName`, `Status`, `Protocol`|PT1M |Yes|
|**Devices assigned**<p><p>Number of devices assigned to an IoT hub |`DeviceAssignments` |Count |Total |`ProvisioningServiceName`, `IotHubName`|PT1M |Yes|
|**Registration attempts**<p><p>Number of device registrations attempted |`RegistrationAttempts` |Count |Total |`ProvisioningServiceName`, `IotHubName`, `Status`|PT1M |Yes|