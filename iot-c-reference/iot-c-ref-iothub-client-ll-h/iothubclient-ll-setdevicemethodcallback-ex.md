# IoTHubClient_LL_SetDeviceMethodCallback_Ex()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_client_ll.h"](../iot-c-ref-iothub-client-ll-h.md)  

**[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClient_LL_SetDeviceMethodCallback_Ex](#iothub__client__ll_8h_1a93d4fa3242a15429e6cf6e0d7c65da9e)([IOTHUB_CLIENT_LL_HANDLE](#iothub__client__ll_8h_1abdbc7b1e6f374be8f2339d8c93f87742) iotHubClientHandle,[IOTHUB_CLIENT_INBOUND_DEVICE_METHOD_CALLBACK](#iothub__client__core__common_8h_1a43072ecc913e5ca776108b1731553c30) inboundDeviceMethodCallback,void * userContextCallback)**

This API sets callback for async cloud to device method call.

#### Parameters
* `iotHubClientHandle` The handle created by a call to the create function. 

* `inboundDeviceMethodCallback` The callback which will be called by IoTHub. 

* `userContextCallback` User specified context that will be provided to the callback. This can be `NULL`.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

