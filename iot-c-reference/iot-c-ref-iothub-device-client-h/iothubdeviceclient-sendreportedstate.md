# IoTHubDeviceClient_SendReportedState()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_device_client.h"](../iot-c-ref-iothub-device-client-h.md)  

[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubDeviceClient_SendReportedState`](#iothub__device__client_8h_1a8b0347cae8cb353e14d210fef0ab410e)(`[`IOTHUB_DEVICE_CLIENT_HANDLE`](#iothub__device__client_8h_1ac0a6393bbcbec2e1b580e8c4c127f4c1) iotHubClientHandle,const unsigned char * reportedState,size_t size,`[`IOTHUB_CLIENT_REPORTED_STATE_CALLBACK`](#iothub__client__core__common_8h_1a9ae117da9222a5138e31a8953ce18bbc) reportedStateCallback,void * userContextCallback)`

This API sends a report of the device's properties and their current values.

#### Parameters
* `iotHubClientHandle` The handle created by a call to the create function. 

* `reportedState` The current device property values to be 'reported' to the IoTHub. 

* `reportedStateCallback` The callback specified by the device client to be called with the result of the transaction. 

* `userContextCallback` User specified context that will be provided to the callback. This can be `NULL`.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubDeviceClient_Destroy](#iothub__device__client_8h_1a2991e03140462e9cc1606ccf25e8b412) function from within any callback.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

