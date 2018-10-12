# IoTHubRegistryManager_DeleteModule()

Deletes a given module.

## Syntax

\#include "[azure-iot-sdk-c/iothub_service_client/inc/iothub_registrymanager.h](../iot-c-ref-iothub-registrymanager-h.md)"  
```C
IOTHUB_REGISTRYMANAGER_RESULT IoTHubRegistryManager_DeleteModule(
  IOTHUB_REGISTRYMANAGER_HANDLE  registryManagerHandle,
  const char *                   deviceId,
  const char *                   moduleId
);
```

## Parameters
* `registryManagerHandle` The handle created by a call to the create function. 

* `deviceId` The Id of the device containing module to delete. 

* `moduleId` The Id of the module to delete.

## Return Value
IOTHUB_REGISTRYMANAGER_RESULT_OK upon success or an error code upon failure.

