# IoTHubDeviceClient_LL_Destroy()

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_device_client_ll.h](../iot-c-ref-iothub-device-client-ll-h.md)"  

## Syntax

```C
void IoTHubDeviceClient_LL_Destroy(
  IOTHUB_DEVICE_CLIENT_LL_HANDLE  iotHubClientHandle);
```

Disposes of resources allocated by the IoT Hub client. This is a blocking call.

## Parameters
* `iotHubClientHandle`The handle created by a call to the create function.

