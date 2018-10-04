# IoTHubMessage_GetConnectionModuleId()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_message.h"](../iot-c-ref-iothub-message-h.md)  

const char * `[`IoTHubMessage_GetConnectionModuleId`](#iothub__message_8h_1ad4dc37f28c9b4f82e6ab63bcca83e19b)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle)`

Gets the module name from the IOTHUB_MESSAGE_HANDLE.

#### Parameters
* `iotHubMessageHandle` Handle to the message.

#### Returns
A const char* pointing to the connection module Id.

