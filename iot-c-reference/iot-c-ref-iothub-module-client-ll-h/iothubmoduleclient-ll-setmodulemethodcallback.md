# IoTHubModuleClient_LL_SetModuleMethodCallback()

This API sets callback for async cloud to module method call.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_module_client_ll.h](../iot-c-ref-iothub-module-client-ll-h.md)"  
```C
IOTHUB_CLIENT_RESULT IoTHubModuleClient_LL_SetModuleMethodCallback(
  IOTHUB_MODULE_CLIENT_LL_HANDLE              iotHubModuleClientHandle,
  IOTHUB_CLIENT_DEVICE_METHOD_CALLBACK_ASYNC  moduleMethodCallback,
  void *                                      userContextCallback
);
```

## Parameters
* `iotHubModuleClientHandle` The handle created by a call to the create function. 

* `moduleMethodCallback` The callback which will be called by IoTHub. 

* `userContextCallback` User specified context that will be provided to the callback. This can be `NULL`.

## Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

