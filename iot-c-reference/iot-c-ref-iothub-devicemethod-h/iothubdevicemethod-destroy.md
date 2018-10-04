# IoTHubDeviceMethod_Destroy()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_devicemethod.h"](../iot-c-ref-iothub-devicemethod-h.md)  

## Syntax

```C
void IoTHubDeviceMethod_Destroy(
  IOTHUB_SERVICE_CLIENT_DEVICE_METHOD_HANDLE	serviceClientDeviceMethodHandle
);

```

Disposes of resources allocated by the IoT Hub IoTHubDeviceMethod_Create.

#### Parameters
* `serviceClientDeviceMethodHandle` The handle created by a call to the create function.

