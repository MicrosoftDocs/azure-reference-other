# IoTHubDeviceClient_GetLastMessageReceiveTime()

This function returns in the out parameter `lastMessageReceiveTime` what was the value of the `time` function when the last message was received at the client.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_device_client.h](../iot-c-ref-iothub-device-client-h.md)"  
```C
IOTHUB_CLIENT_RESULT IoTHubDeviceClient_GetLastMessageReceiveTime(
  IOTHUB_DEVICE_CLIENT_HANDLE  iotHubClientHandle,
  time_t *                     lastMessageReceiveTime
);
```

## Parameters
* `iotHubClientHandle` The handle created by a call to the create function. 

* `lastMessageReceiveTime` Out parameter containing the value of `time` function when the last message was received.

## Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

