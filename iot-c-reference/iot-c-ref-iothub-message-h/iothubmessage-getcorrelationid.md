# IoTHubMessage_GetCorrelationId()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_message.h"](../iot-c-ref-iothub-message-h.md)  

**const char * [IoTHubMessage_GetCorrelationId](#iothub__message_8h_1aac9f6f33fc89f91ffa7853692a1555b6)([IOTHUB_MESSAGE_HANDLE](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle)**

Gets the CorrelationId from the IOTHUB_MESSAGE_HANDLE.

#### Parameters
* `iotHubMessageHandle` Handle to the message.

#### Returns
A const char* pointing to the Correlation Id.

