# IoTHubDeviceClient_Destroy()

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_device_client.h](../iot-c-ref-iothub-device-client-h.md)"  

## Syntax

```C
void IoTHubDeviceClient_Destroy(
  IOTHUB_DEVICE_CLIENT_HANDLE  iotHubClientHandle
);
```

Disposes of resources allocated by the IoT Hub client. This is a blocking call.

## Parameters
* **:iotHubClientHandle** The handle created by a call to the create function.

