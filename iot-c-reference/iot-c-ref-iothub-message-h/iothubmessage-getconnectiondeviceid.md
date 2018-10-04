# IoTHubMessage_GetConnectionDeviceId()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_message.h"](../iot-c-ref-iothub-message-h.md)  

const char * `[`IoTHubMessage_GetConnectionDeviceId`](#iothub__message_8h_1a1e04618fe0efb5981c8bc744bd360d76)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle)`

Gets the connection device ID from the IOTHUB_MESSAGE_HANDLE.

#### Parameters
* `iotHubMessageHandle` Handle to the message.

#### Returns
A const char* pointing to the connection device Id.

