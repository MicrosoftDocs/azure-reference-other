# IoTHubMessage_GetContentType()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_message.h"](../iot-c-ref-iothub-message-h.md)  

[`IOTHUBMESSAGE_CONTENT_TYPE`](#iothub__message_8h_1aea6d5176bef9e4c53f015b35f5f32d16) `[`IoTHubMessage_GetContentType`](#iothub__message_8h_1ae7fd8e5a5844a4346933a86feb577d3c)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle)`

Returns the content type of the message given by parameter `iotHubMessageHandle`.

#### Parameters
* `iotHubMessageHandle` Handle to the message.

This function retrieves the standardized type of the payload, which indicates if `iotHubMessageHandle` was created using a String or a Byte Array.

#### Returns
An `IOTHUBMESSAGE_CONTENT_TYPE` value.

