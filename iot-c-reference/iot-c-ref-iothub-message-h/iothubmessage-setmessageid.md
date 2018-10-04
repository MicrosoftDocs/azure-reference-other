# IoTHubMessage_SetMessageId()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_message.h"](../iot-c-ref-iothub-message-h.md)  

[`IOTHUB_MESSAGE_RESULT`](#iothub__message_8h_1a9ecf3d22e0ef357c3e7eda387ea07f62) `[`IoTHubMessage_SetMessageId`](#iothub__message_8h_1a3d5f3d8a6da59b259f170de613c61cc0)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle,const char * messageId)`

Sets the MessageId for the IOTHUB_MESSAGE_HANDLE.

#### Parameters
* `iotHubMessageHandle` Handle to the message. 

* `messageId` Pointer to the memory location of the messageId

#### Returns
Returns IOTHUB_MESSAGE_OK if the messageId was set successfully or an error code otherwise.

