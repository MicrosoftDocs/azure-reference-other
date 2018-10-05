# IoTHubDeviceClient_SetDeviceMethodCallback()

This API sets the callback for async cloud to device method calls.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_device_client.h](../iot-c-ref-iothub-device-client-h.md)"  
```C
IOTHUB_CLIENT_RESULT IoTHubDeviceClient_SetDeviceMethodCallback(
  IOTHUB_DEVICE_CLIENT_HANDLE                 iotHubClientHandle,
  IOTHUB_CLIENT_DEVICE_METHOD_CALLBACK_ASYNC  deviceMethodCallback,
  void *                                      userContextCallback
);
```

## Parameters
* `iotHubClientHandle` The handle created by a call to the create function. 

* `inboundDeviceMethodCallback` The callback which will be called by IoTHub. 

* `userContextCallback` User specified context that will be provided to the callback. This can be `NULL`.

## Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

