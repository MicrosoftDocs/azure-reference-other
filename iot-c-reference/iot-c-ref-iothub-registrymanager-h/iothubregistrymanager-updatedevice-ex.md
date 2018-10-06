# IoTHubRegistryManager_UpdateDevice_Ex()

Updates a device on IoT Hub.

## Syntax

\#include "[azure-iot-sdk-c/iothub_service_client/inc/iothub_registrymanager.h](../iot-c-ref-iothub-registrymanager-h.md)"  
```C
IOTHUB_REGISTRYMANAGER_RESULT IoTHubRegistryManager_UpdateDevice_Ex(
  IOTHUB_REGISTRYMANAGER_HANDLE     registryManagerHandle,
  IOTHUB_REGISTRY_DEVICE_UPDATE_EX  deviceUpdate
);
```

## Parameters
* `registryManagerHandle` The handle created by a call to the create function. 

* `deviceUpdate` [IOTHUB_REGISTRY_DEVICE_UPDATE_EX](#undefined) structure containing the new device Id, primaryKey (optional), secondaryKey (optional), authentication method, and status

## Return Value
IOTHUB_REGISTRYMANAGER_RESULT_OK upon success or an error code upon failure.

