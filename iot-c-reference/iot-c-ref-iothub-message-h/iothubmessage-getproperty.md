# IoTHubMessage_GetProperty()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_message.h"](../iot-c-ref-iothub-message-h.md)  

const char * `[`IoTHubMessage_GetProperty`](#iothub__message_8h_1ab3deb99bb741380be15ae8dcdcee6316)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle,const char * key)`

Gets a IotHub Message's properties item.

#### Parameters
* `iotHubMessageHandle` Handle to the message.

* `key` name of the property to retrieve.

#### Returns
A string with the property's value, or NULL if it does not exist in the properties list.

