# IoTHubModuleClient_SetModuleMethodCallback()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_module_client.h"](../iot-c-ref-iothub-module-client-h.md)  

**[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubModuleClient_SetModuleMethodCallback](#iothub__module__client_8h_1a4aeb01ee89b410395815b025fc5df966)([IOTHUB_MODULE_CLIENT_HANDLE](#iothub__module__client_8h_1a61259310a513ae73b31cb3c66d3f4087) IoTHubClientHandle,[IOTHUB_CLIENT_DEVICE_METHOD_CALLBACK_ASYNC](#iothub__client__core__common_8h_1aa758c6c04994938fae9257289760d01a) methodCallback,void * userContextCallback)**

This API sets callback for async cloud to module method call.

#### Parameters
* `IoTHubClientHandle` The handle created by a call to the create function. 

* `methodCallback` The callback which will be called by IoTHub. 

* `userContextCallback` User specified context that will be provided to the callback. This can be `NULL`.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

