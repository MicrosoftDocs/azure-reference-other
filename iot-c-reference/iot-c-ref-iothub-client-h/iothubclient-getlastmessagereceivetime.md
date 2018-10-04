# IoTHubClient_GetLastMessageReceiveTime()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_client.h"](../iot-c-ref-iothub-client-h.md)  

## Syntax

```C
IOTHUB_CLIENT_RESULT IoTHubClient_GetLastMessageReceiveTime(
  IOTHUB_CLIENT_HANDLE  	iotHubClientHandle,
  time_t *              	lastMessageReceiveTime
);

```

This function returns in the out parameter `lastMessageReceiveTime` what was the value of the `time` function when the last message was received at the client.

#### Parameters
* `iotHubClientHandle` The handle created by a call to the create function. 

* `lastMessageReceiveTime` Out parameter containing the value of `time` function when the last message was received.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

