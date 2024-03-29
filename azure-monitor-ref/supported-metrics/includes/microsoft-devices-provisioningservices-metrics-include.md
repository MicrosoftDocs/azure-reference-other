---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Devices/provisioningServices, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Attestation attempts**<br><br>Number of device attestations attempted |`AttestationAttempts` |Count |Total |`ProvisioningServiceName`, `Status`, `Protocol`|PT1M |Yes|
|**Devices assigned**<br><br>Number of devices assigned to an IoT hub |`DeviceAssignments` |Count |Total |`ProvisioningServiceName`, `IotHubName`|PT1M |Yes|
|**Registration attempts**<br><br>Number of device registrations attempted |`RegistrationAttempts` |Count |Total |`ProvisioningServiceName`, `IotHubName`, `Status`|PT1M |Yes|