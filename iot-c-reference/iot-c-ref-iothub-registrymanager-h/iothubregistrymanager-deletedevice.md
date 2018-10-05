# IoTHubRegistryManager_DeleteDevice()

Deletes a given device.

## Syntax

\#include "[azure-iot-sdk-c/iothub_service_client/inc/iothub_registrymanager.h](../iot-c-ref-iothub-registrymanager-h.md)"  
```C
IOTHUB_REGISTRYMANAGER_RESULT IoTHubRegistryManager_DeleteDevice(
  IOTHUB_REGISTRYMANAGER_HANDLE  registryManagerHandle,
  const char *                   deviceId
);
```

## Parameters
* `registryManagerHandle` The handle created by a call to the create function. 

* `deviceId` The Id of the device to delete.

## Returns
IOTHUB_REGISTRYMANAGER_RESULT_OK upon success or an error code upon failure.

