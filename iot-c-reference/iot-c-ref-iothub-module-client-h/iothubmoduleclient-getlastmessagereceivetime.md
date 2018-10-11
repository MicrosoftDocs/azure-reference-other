# IoTHubModuleClient_GetLastMessageReceiveTime()

This function returns in the out parameter lastMessageReceiveTime what was the value of the time function when the last message was received at the client.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_module_client.h](../iot-c-ref-iothub-module-client-h.md)"  
```C
IOTHUB_CLIENT_RESULT IoTHubModuleClient_GetLastMessageReceiveTime(
  IOTHUB_MODULE_CLIENT_HANDLE  iotHubModuleClientHandle,
  time_t *                     lastMessageReceiveTime
);
```

## Parameters
* `iotHubModuleClientHandle` The handle created by a call to the create function. 

* `lastMessageReceiveTime` Out parameter containing the value of time function when the last message was received.

## Return Value
IOTHUB_CLIENT_OK upon success or an error code upon failure.

