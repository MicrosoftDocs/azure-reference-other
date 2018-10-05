# IoTHubRegistryManager_GetDevice_Ex()

\#include "[azure-iot-sdk-c/iothub_service_client/inc/iothub_registrymanager.h](../iot-c-ref-iothub-registrymanager-h.md)"  

## Syntax

```C
IOTHUB_REGISTRYMANAGER_RESULT IoTHubRegistryManager_GetDevice_Ex(
  IOTHUB_REGISTRYMANAGER_HANDLE  registryManagerHandle,

  const char *                   deviceId,

  IOTHUB_DEVICE_EX               device
);
```

Gets device info for a given device.

## Parameters
* **:registryManagerHandle** The handle created by a call to the create function. 

* **:deviceId** The Id of the requested device. 

* **:device** Input parameter, if it is not NULL will contain the requested device info structure

## Returns
IOTHUB_REGISTRYMANAGER_RESULT_OK upon success or an error code upon failure.

