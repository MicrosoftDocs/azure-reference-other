# IoTHubRegistryManager_DeleteDevice()

\#include "[azure-iot-sdk-c/iothub_service_client/inc/iothub_registrymanager.h](../iot-c-ref-iothub-registrymanager-h.md)"  

## Syntax

```C
IOTHUB_REGISTRYMANAGER_RESULT IoTHubRegistryManager_DeleteDevice(
  IOTHUB_REGISTRYMANAGER_HANDLE  registryManagerHandle,
  const char *                   deviceId);
```

Deletes a given device.

## Parameters
* `registryManagerHandle`The handle created by a call to the create function. 

* `deviceId`The Id of the device to delete.

## Returns
IOTHUB_REGISTRYMANAGER_RESULT_OK upon success or an error code upon failure.

