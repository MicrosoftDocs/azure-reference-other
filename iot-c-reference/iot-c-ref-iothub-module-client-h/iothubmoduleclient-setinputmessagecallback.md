# IoTHubModuleClient_SetInputMessageCallback()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_module_client.h"](../iot-c-ref-iothub-module-client-h.md)  

[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubModuleClient_SetInputMessageCallback`](#iothub__module__client_8h_1a59375cb047c4b696e5eb8bfb9075fd5b)(`[`IOTHUB_MODULE_CLIENT_HANDLE`](#iothub__module__client_8h_1a61259310a513ae73b31cb3c66d3f4087) iotHubModuleClientHandle,const char * inputName,`[`IOTHUB_CLIENT_MESSAGE_CALLBACK_ASYNC`](#iothub__client__core__common_8h_1adf7097e8fc9e34f26dd9347d4eaa5f8d) eventHandlerCallback,void * userContextCallback)`

This API sets callback for method call that is directed to specified 'inputName' queue (e.g. messages from IoTHubClient_SendEventToOutputAsync)

#### Parameters
* `iotHubModuleClientHandle` The handle created by a call to the create function. 

* `inputName` The name of the queue to listen on for this moduleMethodCallback/userContextCallback. 

* `eventHandlerCallback` The callback which will be called by IoTHub. 

* `userContextCallback` User specified context that will be provided to the callback. This can be `NULL`.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

