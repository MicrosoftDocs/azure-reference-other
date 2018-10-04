# IoTHubMessage_Clone()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_message.h"](../iot-c-ref-iothub-message-h.md)  

[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) `[`IoTHubMessage_Clone`](#iothub__message_8h_1ab5c68ff6fbb9dbe613c8b981f4c202b4)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle)`

Creates a new IoT hub message with the content identical to that of the `iotHubMessageHandle` parameter.

#### Parameters
* `iotHubMessageHandle` Handle to the message that is to be cloned.

#### Returns
A valid `IOTHUB_MESSAGE_HANDLE` if the message was successfully cloned or `NULL` in case an error occurs.

