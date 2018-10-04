# IoTHubMessage_Properties()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_message.h"](../iot-c-ref-iothub-message-h.md)  

[`MAP_HANDLE`](#map_8h_1aaa6ea96fbf2e858b6b2cfe4c7fe31a46) `[`IoTHubMessage_Properties`](#iothub__message_8h_1a2ab46db5ad9db0b497b5171e21b64ea2)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle)`

Gets a handle to the message's properties map. Note that when sending messages via the HTTP transport, the key names in the map must not contain spaces.

DEPRECATED: Use IoTHubMessage_SetProperty and IoTHubMessage_GetProperty instead. ** 
#### Parameters
* `iotHubMessageHandle` Handle to the message.

#### Returns
A `MAP_HANDLE` pointing to the properties map for this message.

