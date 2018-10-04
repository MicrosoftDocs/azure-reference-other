# IoTHubDeviceClient_LL_SetDeviceMethodCallback()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_device_client_ll.h"](../iot-c-ref-iothub-device-client-ll-h.md)  

## Syntax

```C
IOTHUB_CLIENT_RESULT IoTHubDeviceClient_LL_SetDeviceMethodCallback(
  IOTHUB_DEVICE_CLIENT_LL_HANDLE	iotHubClientHandle,
  IOTHUB_CLIENT_DEVICE_METHOD_CALLBACK_ASYNC	deviceMethodCallback,
  void *	userContextCallback
);

```

This API sets the callback for async cloud to device method calls.

#### Parameters
* `iotHubClientHandle` The handle created by a call to the create function. 

* `inboundDeviceMethodCallback` The callback which will be called by IoTHub. 

* `userContextCallback` User specified context that will be provided to the callback. This can be `NULL`.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

