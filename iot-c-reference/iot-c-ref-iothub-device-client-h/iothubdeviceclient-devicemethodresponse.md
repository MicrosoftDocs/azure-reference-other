# IoTHubDeviceClient_DeviceMethodResponse()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_device_client.h"](../iot-c-ref-iothub-device-client-h.md)  

**[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubDeviceClient_DeviceMethodResponse](#iothub__device__client_8h_1a0a0909124da66a5d0dcd5c172fe7eaea)([IOTHUB_DEVICE_CLIENT_HANDLE](#iothub__device__client_8h_1ac0a6393bbcbec2e1b580e8c4c127f4c1) iotHubClientHandle,[METHOD_HANDLE](#iothub__transport__ll_8h_1a1cc79695294f89e97fb945066a3b3d77) methodId,const unsigned char * response,size_t response_size,int statusCode)**

This API responds to an asnyc method callback identified the methodId.

#### Parameters
* `iotHubClientHandle` The handle created by a call to the create function. 

* `methodId` The methodId of the Device Method callback. 

* `response` The response data for the method callback. 

* `response_size` The size of the response data buffer. 

* `status_response` The status response of the method callback.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

