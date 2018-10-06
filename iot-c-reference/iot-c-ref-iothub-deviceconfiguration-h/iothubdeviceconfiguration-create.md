# IoTHubDeviceConfiguration_Create()

Creates a IoT Hub Service Client DeviceConfiguration handle for use it in consequent APIs.

## Syntax

\#include "[azure-iot-sdk-c/iothub_service_client/inc/iothub_deviceconfiguration.h](../iot-c-ref-iothub-deviceconfiguration-h.md)"  
```C
IOTHUB_SERVICE_CLIENT_DEVICE_CONFIGURATION_HANDLE IoTHubDeviceConfiguration_Create(
  IOTHUB_SERVICE_CLIENT_AUTH_HANDLE  serviceClientHandle
);
```

## Parameters
* `serviceClientHandle` Service client handle.

## Return Value
A non-NULL `IOTHUB_SERVICE_CLIENT_DEVICE_CONFIGURATION_HANDLE` value that is used when invoking other functions for IoT Hub DeviceConfiguration and `NULL` on failure.

