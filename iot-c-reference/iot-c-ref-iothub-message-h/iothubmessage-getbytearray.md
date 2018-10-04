# IoTHubMessage_GetByteArray()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_message.h"](../iot-c-ref-iothub-message-h.md)  

[`IOTHUB_MESSAGE_RESULT`](#iothub__message_8h_1a9ecf3d22e0ef357c3e7eda387ea07f62) `[`IoTHubMessage_GetByteArray`](#iothub__message_8h_1afac0461ed8c3d522bbf2a4cfa9f3f957)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle,const unsigned char ** buffer,size_t * size)`

Fetches a pointer and size for the data associated with the IoT hub message handle. If the content type of the message is not `IOTHUBMESSAGE_BYTEARRAY` then the function returns `IOTHUB_MESSAGE_INVALID_ARG`.

#### Parameters
* `iotHubMessageHandle` Handle to the message. 

* `buffer` Pointer to the memory location where the pointer to the buffer will be written. 

* `size` The size of the buffer will be written to this address.

#### Returns
Returns IOTHUB_MESSAGE_OK if the byte array was fetched successfully or an error code otherwise.

