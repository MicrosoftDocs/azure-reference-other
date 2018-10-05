# IoTHubDeviceClient_LL_GetLastMessageReceiveTime()

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_device_client_ll.h](../iot-c-ref-iothub-device-client-ll-h.md)"  

## Syntax

```C
IOTHUB_CLIENT_RESULT IoTHubDeviceClient_LL_GetLastMessageReceiveTime(
  IOTHUB_DEVICE_CLIENT_LL_HANDLE  iotHubClientHandle,

  time_t *                        lastMessageReceiveTime
);
```

This function returns in the out parameter `lastMessageReceiveTime` what was the value of the `time` function when the last message was received at the client.

## Parameters
* **:iotHubClientHandle** The handle created by a call to the create function. 

* **:lastMessageReceiveTime** Out parameter containing the value of `time` function when the last message was received.

## Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

