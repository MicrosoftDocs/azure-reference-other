# IoTHubModuleClient_SetModuleTwinCallback()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_module_client.h"](../iot-c-ref-iothub-module-client-h.md)  

**[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubModuleClient_SetModuleTwinCallback](#iothub__module__client_8h_1abc3d460b7d976dabc757d9dda0f96463)([IOTHUB_MODULE_CLIENT_HANDLE](#iothub__module__client_8h_1a61259310a513ae73b31cb3c66d3f4087) iotHubModuleClientHandle,[IOTHUB_CLIENT_DEVICE_TWIN_CALLBACK](#iothub__client__core__common_8h_1a3020471f05025405840d9c43466122dc) moduleTwinCallback,void * userContextCallback)**

This API specifies a call back to be used when the module receives a state update.

#### Parameters
* `iotHubModuleClientHandle` The handle created by a call to the create function. 

* `moduleTwinCallback` The callback specified by the module client to be used for updating the desired state. The callback will be called in response to a request send by the IoTHub services. The payload will be passed to the callback, along with two version numbers:

* Desired:

* LastSeenReported: 

* `userContextCallback` User specified context that will be provided to the callback. This can be `NULL`.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubModuleClient_Destroy](#iothub__module__client_8h_1af70545d139f41f0bc8acb51725c2d0de) function from within any callback.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

