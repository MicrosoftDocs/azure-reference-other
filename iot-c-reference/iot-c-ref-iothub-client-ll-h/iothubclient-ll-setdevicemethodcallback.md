# IoTHubClient_LL_SetDeviceMethodCallback()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_client_ll.h"](../iot-c-ref-iothub-client-ll-h.md)  

[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubClient_LL_SetDeviceMethodCallback`](#iothub__client__ll_8h_1ae7a7582ea0ea061418f21bab3d236a1d)(`[`IOTHUB_CLIENT_LL_HANDLE`](#iothub__client__ll_8h_1abdbc7b1e6f374be8f2339d8c93f87742) iotHubClientHandle,`[`IOTHUB_CLIENT_DEVICE_METHOD_CALLBACK_ASYNC`](#iothub__client__core__common_8h_1aa758c6c04994938fae9257289760d01a) deviceMethodCallback,void * userContextCallback)`

This API sets callback for cloud to device method call.

#### Parameters
* `iotHubClientHandle` The handle created by a call to the create function. 

* `deviceMethodCallback` The callback which will be called by IoTHub. 

* `userContextCallback` User specified context that will be provided to the callback. This can be `NULL`.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

