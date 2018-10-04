# IoTHubModuleClient_SendEventAsync()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_module_client.h"](../iot-c-ref-iothub-module-client-h.md)  

[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubModuleClient_SendEventAsync`](#iothub__module__client_8h_1a512d1335ba02912fed91a8ea00f0bd67)(`[`IOTHUB_MODULE_CLIENT_HANDLE`](#iothub__module__client_8h_1a61259310a513ae73b31cb3c66d3f4087) iotHubModuleClientHandle,`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) eventMessageHandle,`[`IOTHUB_CLIENT_EVENT_CONFIRMATION_CALLBACK`](#iothub__client__core__common_8h_1a41b17fcb2cb70587e3576226561648a0) eventConfirmationCallback,void * userContextCallback)`

Asynchronous call to send the message specified by `eventMessageHandle`.

#### Parameters
* `iotHubModuleClientHandle` The handle created by a call to the create function. 

* `eventMessageHandle` The handle to an IoT Hub message. 

* `eventConfirmationCallback` The callback specified by the module for receiving confirmation of the delivery of the IoT Hub message. This callback can be expected to invoke the [IoTHubModuleClient_SendEventAsync](#iothub__module__client_8h_1a512d1335ba02912fed91a8ea00f0bd67) function for the same message in an attempt to retry sending a failing message. The user can specify a `NULL` value here to indicate that no callback is required. 

* `userContextCallback` User specified context that will be provided to the callback. This can be `NULL`.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubModuleClient_Destroy](#iothub__module__client_8h_1af70545d139f41f0bc8acb51725c2d0de) function from within any callback.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

