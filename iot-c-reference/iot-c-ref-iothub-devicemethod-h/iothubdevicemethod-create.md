# IoTHubDeviceMethod_Create()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_devicemethod.h"](../iot-c-ref-iothub-devicemethod-h.md)  

## Syntax

```C
IOTHUB_SERVICE_CLIENT_DEVICE_METHOD_HANDLE IoTHubDeviceMethod_Create(
  IOTHUB_SERVICE_CLIENT_AUTH_HANDLE  	serviceClientHandle
);

```

Creates a IoT Hub Service Client DeviceMethod handle for use it in consequent APIs.

#### Parameters
* `serviceClientHandle` Service client handle.

#### Returns
A non-NULL `IOTHUB_SERVICE_CLIENT_DEVICE_METHOD_HANDLE` value that is used when invoking other functions for IoT Hub DeviceMethod and `NULL` on failure.

