# IoTHubRegistryManager_Create()

Creates a IoT Hub Registry Manager handle for use it in consequent APIs.

## Syntax

\#include "[azure-iot-sdk-c/iothub_service_client/inc/iothub_registrymanager.h](../iot-c-ref-iothub-registrymanager-h.md)"  
```C
IOTHUB_REGISTRYMANAGER_HANDLE IoTHubRegistryManager_Create(
  IOTHUB_SERVICE_CLIENT_AUTH_HANDLE  serviceClientHandle
);
```

## Parameters
* `serviceClientHandle` Service client handle.

## Return Value
A non-NULL IOTHUB_REGISTRYMANAGER_HANDLE value that is used when invoking other functions for IoT Hub REgistry Manager and NULL on failure.

