# IoTHubDeviceTwin_Create()

Creates a IoT Hub Service Client DeviceTwin handle for use it in consequent APIs.

## Syntax

\#include "[azure-iot-sdk-c/iothub_service_client/inc/iothub_devicetwin.h](../iot-c-ref-iothub-devicetwin-h.md)"  
```C
IOTHUB_SERVICE_CLIENT_DEVICE_TWIN_HANDLE IoTHubDeviceTwin_Create(
  IOTHUB_SERVICE_CLIENT_AUTH_HANDLE  serviceClientHandle
);
```

## Parameters
* `serviceClientHandle` Service client handle.

## Returns
A non-NULL `IOTHUB_SERVICE_CLIENT_DEVICE_TWIN_HANDLE` value that is used when invoking other functions for IoT Hub DeviceTwin and `NULL` on failure.

