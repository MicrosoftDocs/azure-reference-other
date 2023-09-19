---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Devices/provisioningServices, arm
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Attestation attempts<p><p>Number of device attestations attempted |`AttestationAttempts` |Count |Total |ProvisioningServiceName, Status, Protocol|PT1M |Yes|
|Devices assigned<p><p>Number of devices assigned to an IoT hub |`DeviceAssignments` |Count |Total |ProvisioningServiceName, IotHubName|PT1M |Yes|
|Registration attempts<p><p>Number of device registrations attempted |`RegistrationAttempts` |Count |Total |ProvisioningServiceName, IotHubName, Status|PT1M |Yes|