# IoTHubClient_SendEventAsync()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_client.h"](../iot-c-ref-iothub-client-h.md)  

[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubClient_SendEventAsync`](#iothub__client_8h_1a3e60e953d03a503c1ae30dd6af7f390f)(`[`IOTHUB_CLIENT_HANDLE`](#iothub__client_8h_1a228b1409767f2560aa0724caad86fd6d) iotHubClientHandle,`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) eventMessageHandle,`[`IOTHUB_CLIENT_EVENT_CONFIRMATION_CALLBACK`](#iothub__client__core__common_8h_1a41b17fcb2cb70587e3576226561648a0) eventConfirmationCallback,void * userContextCallback)`

Asynchronous call to send the message specified by `eventMessageHandle`.

#### Parameters
* `iotHubClientHandle` The handle created by a call to the create function. 

* `eventMessageHandle` The handle to an IoT Hub message. 

* `eventConfirmationCallback` The callback specified by the device for receiving confirmation of the delivery of the IoT Hub message. This callback can be expected to invoke the [IoTHubClient_SendEventAsync](#iothub__client_8h_1a3e60e953d03a503c1ae30dd6af7f390f) function for the same message in an attempt to retry sending a failing message. The user can specify a `NULL` value here to indicate that no callback is required. 

* `userContextCallback` User specified context that will be provided to the callback. This can be `NULL`.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubClient_Destroy](#iothub__client_8h_1a47fce212d1c5026e02ccd670242e1d83) function from within any callback.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

