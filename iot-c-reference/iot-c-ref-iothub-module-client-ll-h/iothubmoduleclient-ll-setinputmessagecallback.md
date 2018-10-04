# IoTHubModuleClient_LL_SetInputMessageCallback()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_module_client_ll.h"](../iot-c-ref-iothub-module-client-ll-h.md)  

**[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubModuleClient_LL_SetInputMessageCallback](#iothub__module__client__ll_8h_1a54f3398271f5be3f21c0ed41574b2f82)([IOTHUB_MODULE_CLIENT_LL_HANDLE](#iothub__module__client__ll_8h_1ae1a6187aacbdb56cde026ad3d228420a) iotHubModuleClientHandle,const char * inputName,[IOTHUB_CLIENT_MESSAGE_CALLBACK_ASYNC](#iothub__client__core__common_8h_1adf7097e8fc9e34f26dd9347d4eaa5f8d) eventHandlerCallback,void * userContextCallback)**

This API sets callback for method call that is directed to specified 'inputName' queue (e.g. messages from IoTHubClient_SendEventToOutputAsync)

#### Parameters
* `iotHubModuleClientHandle` The handle created by a call to the create function. 

* `inputName` The name of the queue to listen on for this moduleMethodCallback/userContextCallback. 

* `eventHandlerCallback` The callback which will be called by IoTHub. 

* `userContextCallback` User specified context that will be provided to the callback. This can be `NULL`.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

