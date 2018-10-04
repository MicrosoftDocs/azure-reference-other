# IoTHubModuleClient_SendReportedState()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_module_client.h"](../iot-c-ref-iothub-module-client-h.md)  

[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubModuleClient_SendReportedState`](#iothub__module__client_8h_1a7bda16f4d71137f66482ac48f08299b7)(`[`IOTHUB_MODULE_CLIENT_HANDLE`](#iothub__module__client_8h_1a61259310a513ae73b31cb3c66d3f4087) iotHubModuleClientHandle,const unsigned char * reportedState,size_t size,`[`IOTHUB_CLIENT_REPORTED_STATE_CALLBACK`](#iothub__client__core__common_8h_1a9ae117da9222a5138e31a8953ce18bbc) reportedStateCallback,void * userContextCallback)`

This API sends a report of the module's properties and their current values.

#### Parameters
* `iotHubModuleClientHandle` The handle created by a call to the create function. 

* `reportedState` The current module property values to be 'reported' to the IoTHub. 

* `reportedStateCallback` The callback specified by the module client to be called with the result of the transaction. 

* `userContextCallback` User specified context that will be provided to the callback. This can be `NULL`.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubModuleClient_Destroy](#iothub__module__client_8h_1af70545d139f41f0bc8acb51725c2d0de) function from within any callback.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

