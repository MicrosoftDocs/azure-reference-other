# IoTHubMessage_SetProperty()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_message.h"](../iot-c-ref-iothub-message-h.md)  

**[IOTHUB_MESSAGE_RESULT](#iothub__message_8h_1a9ecf3d22e0ef357c3e7eda387ea07f62) [IoTHubMessage_SetProperty](#iothub__message_8h_1accde5b88b49e4fd3ebfdf54c97390d88)([IOTHUB_MESSAGE_HANDLE](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle,const char * key,const char * value)**

Sets a property on a Iothub Message.

#### Parameters
* `iotHubMessageHandle` Handle to the message.

* `key` name of the property to set. Note that when sending messages via the HTTP transport, this value must not contain spaces.

* `value` of the property to set.

#### Returns
An `IOTHUB_MESSAGE_RESULT` value indicating the result of setting the property.

