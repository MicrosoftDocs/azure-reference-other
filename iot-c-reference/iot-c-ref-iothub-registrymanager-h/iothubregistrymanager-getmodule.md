# IoTHubRegistryManager_GetModule()

\#include "[azure-iot-sdk-c/iothub_service_client/inc/iothub_registrymanager.h](../iot-c-ref-iothub-registrymanager-h.md)"  

## Syntax

```C
IOTHUB_REGISTRYMANAGER_RESULT IoTHubRegistryManager_GetModule(
  IOTHUB_REGISTRYMANAGER_HANDLE  registryManagerHandle,
  const char *                   deviceId,
  const char *                   moduleId,
  IOTHUB_MODULE                  module);
```

Gets module info for a given module.

## Parameters
* `registryManagerHandle`The handle created by a call to the create function. 

* `deviceId`The Id of the requested device. 

* `moduleId`The Id of the requested module. 

* `module`Input parameter, if it is not NULL will contain the requested module info structure

## Returns
IOTHUB_REGISTRYMANAGER_RESULT_OK upon success or an error code upon failure.

