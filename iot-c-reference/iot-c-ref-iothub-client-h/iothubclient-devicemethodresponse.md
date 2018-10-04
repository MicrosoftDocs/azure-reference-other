# IoTHubClient_DeviceMethodResponse()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_client.h"](../iot-c-ref-iothub-client-h.md)  

[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubClient_DeviceMethodResponse`](#iothub__client_8h_1acab103052c5b960e285c7c5d76d8d28f)(`[`IOTHUB_CLIENT_HANDLE`](#iothub__client_8h_1a228b1409767f2560aa0724caad86fd6d) iotHubClientHandle,`[`METHOD_HANDLE`](#iothub__transport__ll_8h_1a1cc79695294f89e97fb945066a3b3d77) methodId,const unsigned char * response,size_t response_size,int statusCode)`

This API responses to a asnyc method callback identified the methodId.

#### Parameters
* `iotHubClientHandle` The handle created by a call to the create function. 

* `methodId` The methodId of the Device Method callback. 

* `response` The response data for the method callback. 

* `response_size` The size of the response data buffer. 

* `status_response` The status response of the method callback.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

