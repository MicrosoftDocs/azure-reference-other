# IoTHubModuleClient_LL_SetModuleMethodCallback()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_module_client_ll.h"](../iot-c-ref-iothub-module-client-ll-h.md)  

**[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubModuleClient_LL_SetModuleMethodCallback](#iothub__module__client__ll_8h_1a9eb4748db53e83c2d28608599ee6f267)([IOTHUB_MODULE_CLIENT_LL_HANDLE](#iothub__module__client__ll_8h_1ae1a6187aacbdb56cde026ad3d228420a) iotHubModuleClientHandle,[IOTHUB_CLIENT_DEVICE_METHOD_CALLBACK_ASYNC](#iothub__client__core__common_8h_1aa758c6c04994938fae9257289760d01a) moduleMethodCallback,void * userContextCallback)**

This API sets callback for async cloud to module method call.

#### Parameters
* `iotHubModuleClientHandle` The handle created by a call to the create function. 

* `moduleMethodCallback` The callback which will be called by IoTHub. 

* `userContextCallback` User specified context that will be provided to the callback. This can be `NULL`.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

