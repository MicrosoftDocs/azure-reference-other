# IoTHubMessage_SetContentTypeSystemProperty()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_message.h"](../iot-c-ref-iothub-message-h.md)  

**[IOTHUB_MESSAGE_RESULT](#iothub__message_8h_1a9ecf3d22e0ef357c3e7eda387ea07f62) [IoTHubMessage_SetContentTypeSystemProperty](#iothub__message_8h_1af5961a16ad97a128434cbdde78a91b4c)([IOTHUB_MESSAGE_HANDLE](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle,const char * contentType)**

Sets the content-type of the message payload, as per supported values on RFC 2046.

#### Parameters
* `iotHubMessageHandle` Handle to the message.

* `contentType` String defining the type of the payload (e.g., text/plain).

#### Returns
An `IOTHUB_MESSAGE_RESULT` value.

