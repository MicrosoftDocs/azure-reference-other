# IoTHubModuleClient_LL_SendReportedState()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_module_client_ll.h"](../iot-c-ref-iothub-module-client-ll-h.md)  

**[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubModuleClient_LL_SendReportedState](#iothub__module__client__ll_8h_1a44519374217fca11ad0faa4f8e1cb08d)([IOTHUB_MODULE_CLIENT_LL_HANDLE](#iothub__module__client__ll_8h_1ae1a6187aacbdb56cde026ad3d228420a) iotHubModuleClientHandle,const unsigned char * reportedState,size_t size,[IOTHUB_CLIENT_REPORTED_STATE_CALLBACK](#iothub__client__core__common_8h_1a9ae117da9222a5138e31a8953ce18bbc) reportedStateCallback,void * userContextCallback)**

This API sneds a report of the module's properties and their current values.

#### Parameters
* `iotHubModuleClientHandle` The handle created by a call to the create function. 

* `reportedState` The current module property values to be 'reported' to the IoTHub. 

* `reportedStateCallback` The callback specified by the module client to be called with the result of the transaction. 

* `userContextCallback` User specified context that will be provided to the callback. This can be `NULL`.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubModuleClient_LL_Destroy](#iothub__module__client__ll_8h_1aad2dd6c3c24f89a9cfa861754a845138) function from within any callback.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

