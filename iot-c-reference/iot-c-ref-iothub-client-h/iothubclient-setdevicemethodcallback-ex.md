# IoTHubClient_SetDeviceMethodCallback_Ex()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_client.h"](../iot-c-ref-iothub-client-h.md)  

## Syntax

```C
IOTHUB_CLIENT_RESULT IoTHubClient_SetDeviceMethodCallback_Ex(
  IOTHUB_CLIENT_HANDLE                          	iotHubClientHandle,
  IOTHUB_CLIENT_INBOUND_DEVICE_METHOD_CALLBACK  	inboundDeviceMethodCallback,
  void *                                        	userContextCallback
);

```

This API sets callback for async cloud to device method call.

#### Parameters
* `iotHubClientHandle` The handle created by a call to the create function. 

* `inboundDeviceMethodCallback` The callback which will be called by IoTHub. 

* `userContextCallback` User specified context that will be provided to the callback. This can be `NULL`.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

