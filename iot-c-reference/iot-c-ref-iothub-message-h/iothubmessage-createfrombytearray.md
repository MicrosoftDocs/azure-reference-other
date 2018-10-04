# IoTHubMessage_CreateFromByteArray()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_message.h"](../iot-c-ref-iothub-message-h.md)  

[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) `[`IoTHubMessage_CreateFromByteArray`](#iothub__message_8h_1acaa3b835c12fb0254938af052f0fcb6f)(const unsigned char * byteArray,size_t size)`

Creates a new IoT hub message from a byte array. The type of the message will be set to `IOTHUBMESSAGE_BYTEARRAY`.

#### Parameters
* `byteArray` The byte array from which the message is to be created. 

* `size` The size of the byte array.

#### Returns
A valid `IOTHUB_MESSAGE_HANDLE` if the message was successfully created or `NULL` in case an error occurs.

