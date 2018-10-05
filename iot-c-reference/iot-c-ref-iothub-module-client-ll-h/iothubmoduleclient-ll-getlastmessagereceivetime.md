# IoTHubModuleClient_LL_GetLastMessageReceiveTime()

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_module_client_ll.h](../iot-c-ref-iothub-module-client-ll-h.md)"  

## Syntax

```C
IOTHUB_CLIENT_RESULT IoTHubModuleClient_LL_GetLastMessageReceiveTime(
  IOTHUB_MODULE_CLIENT_LL_HANDLE  iotHubModuleClientHandle,

  time_t *                        lastMessageReceiveTime
);
```

This function returns in the out parameter `lastMessageReceiveTime` what was the value of the `time` function when the last message was received at the client.

## Parameters
* **:iotHubModuleClientHandle** The handle created by a call to the create function. 

* **:lastMessageReceiveTime** Out parameter containing the value of `time` function when the last message was received.

## Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

