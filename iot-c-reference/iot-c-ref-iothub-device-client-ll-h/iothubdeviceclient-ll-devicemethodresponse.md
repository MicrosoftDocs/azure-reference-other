# IoTHubDeviceClient_LL_DeviceMethodResponse()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_device_client_ll.h"](../iot-c-ref-iothub-device-client-ll-h.md)  

[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubDeviceClient_LL_DeviceMethodResponse`](#iothub__device__client__ll_8h_1ab7206293126c32eccb7e274d266d4c97)(`[`IOTHUB_DEVICE_CLIENT_LL_HANDLE`](#iothub__device__client__ll_8h_1ab3ed1ccac784de53579181b349fd6616) iotHubClientHandle,`[`METHOD_HANDLE`](#iothub__transport__ll_8h_1a1cc79695294f89e97fb945066a3b3d77) methodId,const unsigned char * response,size_t respSize,int statusCode)`

This API responds to an asnyc method callback identified the methodId.

#### Parameters
* `iotHubClientHandle` The handle created by a call to the create function. 

* `methodId` The methodId of the Device Method callback. 

* `response` The response data for the method callback. 

* `response_size` The size of the response data buffer. 

* `status_response` The status response of the method callback.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

