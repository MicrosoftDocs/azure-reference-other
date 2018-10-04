# IoTHubMessage_GetContentTypeSystemProperty()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_message.h"](../iot-c-ref-iothub-message-h.md)  

const char * `[`IoTHubMessage_GetContentTypeSystemProperty`](#iothub__message_8h_1ab01841e548f7119ab833be50695de241)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle)`

Returns the content-type of the message payload, if defined.

#### Parameters
* `iotHubMessageHandle` Handle to the message.

#### Returns
A string with the content-type value if defined (or NULL otherwise).

