# IoTHubMessage_SetCorrelationId()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_message.h"](../iot-c-ref-iothub-message-h.md)  

[`IOTHUB_MESSAGE_RESULT`](#iothub__message_8h_1a9ecf3d22e0ef357c3e7eda387ea07f62) `[`IoTHubMessage_SetCorrelationId`](#iothub__message_8h_1afcc4a3e4e8ac287b0a9a3850c5a72248)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle,const char * correlationId)`

Sets the CorrelationId for the IOTHUB_MESSAGE_HANDLE.

#### Parameters
* `iotHubMessageHandle` Handle to the message. 

* `correlationId` Pointer to the memory location of the messageId

#### Returns
Returns IOTHUB_MESSAGE_OK if the messageId was set successfully or an error code otherwise.

