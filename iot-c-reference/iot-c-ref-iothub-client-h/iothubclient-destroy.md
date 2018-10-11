# IoTHubClient_Destroy()

Disposes of resources allocated by the IoT Hub client. This is a blocking call.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_client.h](../iot-c-ref-iothub-client-h.md)"  
```C
void IoTHubClient_Destroy(
  IOTHUB_CLIENT_HANDLE  iotHubClientHandle
);
```

## Parameters
* `iotHubClientHandle` The handle created by a call to the create function.

