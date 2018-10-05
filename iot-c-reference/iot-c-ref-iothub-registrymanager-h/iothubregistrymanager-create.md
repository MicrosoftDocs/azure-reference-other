# IoTHubRegistryManager_Create()

\#include "[azure-iot-sdk-c/iothub_service_client/inc/iothub_registrymanager.h](../iot-c-ref-iothub-registrymanager-h.md)"  

## Syntax

```C
IOTHUB_REGISTRYMANAGER_HANDLE IoTHubRegistryManager_Create(
  IOTHUB_SERVICE_CLIENT_AUTH_HANDLE  serviceClientHandle
);
```

Creates a IoT Hub Registry Manager handle for use it in consequent APIs.

## Parameters
* `serviceClientHandle`Service client handle.

## Returns
A non-NULL `IOTHUB_REGISTRYMANAGER_HANDLE` value that is used when invoking other functions for IoT Hub REgistry Manager and `NULL` on failure.

