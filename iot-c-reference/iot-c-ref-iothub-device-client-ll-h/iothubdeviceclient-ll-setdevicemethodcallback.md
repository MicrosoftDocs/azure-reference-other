# IoTHubDeviceClient_LL_SetDeviceMethodCallback()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_device_client_ll.h"](../iot-c-ref-iothub-device-client-ll-h.md)  

[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubDeviceClient_LL_SetDeviceMethodCallback`](#iothub__device__client__ll_8h_1aaaa00ed49441cf566eb94ded6182cab4)(`[`IOTHUB_DEVICE_CLIENT_LL_HANDLE`](#iothub__device__client__ll_8h_1ab3ed1ccac784de53579181b349fd6616) iotHubClientHandle,`[`IOTHUB_CLIENT_DEVICE_METHOD_CALLBACK_ASYNC`](#iothub__client__core__common_8h_1aa758c6c04994938fae9257289760d01a) deviceMethodCallback,void * userContextCallback)`

This API sets the callback for async cloud to device method calls.

#### Parameters
* `iotHubClientHandle` The handle created by a call to the create function. 

* `inboundDeviceMethodCallback` The callback which will be called by IoTHub. 

* `userContextCallback` User specified context that will be provided to the callback. This can be `NULL`.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

