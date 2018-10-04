# IoTHubMessage_SetContentEncodingSystemProperty()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_message.h"](../iot-c-ref-iothub-message-h.md)  

**[IOTHUB_MESSAGE_RESULT](#iothub__message_8h_1a9ecf3d22e0ef357c3e7eda387ea07f62) [IoTHubMessage_SetContentEncodingSystemProperty](#iothub__message_8h_1abd1c044606f8c70df4f1af9b19a7a85f)([IOTHUB_MESSAGE_HANDLE](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle,const char * contentEncoding)**

Sets the content-encoding of the message payload, as per supported values on RFC 2616.

#### Parameters
* `iotHubMessageHandle` Handle to the message.

* `contentEncoding` String defining the encoding of the payload (e.g., utf-8).

#### Returns
An `IOTHUB_MESSAGE_RESULT` value.

