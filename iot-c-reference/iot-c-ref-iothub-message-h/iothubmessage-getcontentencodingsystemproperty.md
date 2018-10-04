# IoTHubMessage_GetContentEncodingSystemProperty()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_message.h"](../iot-c-ref-iothub-message-h.md)  

const char * `[`IoTHubMessage_GetContentEncodingSystemProperty`](#iothub__message_8h_1ab3db6de666d01e3d5730e1d2db592832)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle)`

Returns the content-encoding of the message payload, if defined.

#### Parameters
* `iotHubMessageHandle` Handle to the message.

#### Returns
A string with the content-encoding value if defined (or NULL otherwise).

