# IoTHubClient_LL_SetDeviceMethodCallback()

This API sets callback for cloud to device method call.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_client_ll.h](../iot-c-ref-iothub-client-ll-h.md)"  
```C
IOTHUB_CLIENT_RESULT IoTHubClient_LL_SetDeviceMethodCallback(
  IOTHUB_CLIENT_LL_HANDLE                     iotHubClientHandle,
  IOTHUB_CLIENT_DEVICE_METHOD_CALLBACK_ASYNC  deviceMethodCallback,
  void *                                      userContextCallback
);
```

## Parameters
* `iotHubClientHandle` The handle created by a call to the create function. 

* `deviceMethodCallback` The callback which will be called by IoTHub. 

* `userContextCallback` User specified context that will be provided to the callback. This can be NULL.

## Return Value
IOTHUB_CLIENT_OK upon success or an error code upon failure.

