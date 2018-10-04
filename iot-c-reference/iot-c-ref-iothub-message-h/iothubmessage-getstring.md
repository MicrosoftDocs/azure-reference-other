# IoTHubMessage_GetString()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_message.h"](../iot-c-ref-iothub-message-h.md)  

const char * `[`IoTHubMessage_GetString`](#iothub__message_8h_1aaf63b9aecdde6f8c90d9fbd0755d0c41)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle)`

Returns the null terminated string stored in the message. If the content type of the message is not `IOTHUBMESSAGE_STRING` then the function returns `NULL`.

#### Parameters
* `iotHubMessageHandle` Handle to the message.

#### Returns
`NULL` if an error occurs or a pointer to the stored null terminated string otherwise.

