# IoTHubModuleClient_SetModuleMethodCallback()

This API sets callback for async cloud to module method call.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_module_client.h](../iot-c-ref-iothub-module-client-h.md)"  
```C
IOTHUB_CLIENT_RESULT IoTHubModuleClient_SetModuleMethodCallback(
  IOTHUB_MODULE_CLIENT_HANDLE                 IoTHubClientHandle,
  IOTHUB_CLIENT_DEVICE_METHOD_CALLBACK_ASYNC  methodCallback,
  void *                                      userContextCallback
);
```

## Parameters
* `IoTHubClientHandle` The handle created by a call to the create function. 

* `methodCallback` The callback which will be called by IoTHub. 

* `userContextCallback` User specified context that will be provided to the callback. This can be `NULL`.

## Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

