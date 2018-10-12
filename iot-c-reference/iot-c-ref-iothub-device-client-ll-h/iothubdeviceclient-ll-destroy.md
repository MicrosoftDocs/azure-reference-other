# IoTHubDeviceClient_LL_Destroy()

Disposes of resources allocated by the IoT Hub client. This is a blocking call.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_device_client_ll.h](../iot-c-ref-iothub-device-client-ll-h.md)"  
```C
void IoTHubDeviceClient_LL_Destroy(
  IOTHUB_DEVICE_CLIENT_LL_HANDLE  iotHubClientHandle
);
```

## Parameters
* `iotHubClientHandle` The handle created by a call to the create function.

