# IoTHubModuleClient_LL_SetInputMessageCallback()

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_module_client_ll.h](../iot-c-ref-iothub-module-client-ll-h.md)"  

## Syntax

```C
IOTHUB_CLIENT_RESULT IoTHubModuleClient_LL_SetInputMessageCallback(
  IOTHUB_MODULE_CLIENT_LL_HANDLE        iotHubModuleClientHandle,
  const char *                          inputName,
  IOTHUB_CLIENT_MESSAGE_CALLBACK_ASYNC  eventHandlerCallback,
  void *                                userContextCallback
);
```

This API sets callback for method call that is directed to specified 'inputName' queue (e.g. messages from IoTHubClient_SendEventToOutputAsync)

## Parameters
* `iotHubModuleClientHandle`The handle created by a call to the create function. 

* `inputName`The name of the queue to listen on for this moduleMethodCallback/userContextCallback. 

* `eventHandlerCallback`The callback which will be called by IoTHub. 

* `userContextCallback`User specified context that will be provided to the callback. This can be `NULL`.

## Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

