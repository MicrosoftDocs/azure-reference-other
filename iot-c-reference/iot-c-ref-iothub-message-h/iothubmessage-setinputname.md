# IoTHubMessage_SetInputName()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_message.h"](../iot-c-ref-iothub-message-h.md)  

**[IOTHUB_MESSAGE_RESULT](#iothub__message_8h_1a9ecf3d22e0ef357c3e7eda387ea07f62) [IoTHubMessage_SetInputName](#iothub__message_8h_1aa8dd031bb670f90a791c018bbd6474cd)([IOTHUB_MESSAGE_HANDLE](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle,const char * inputName)**

Sets input for named queues. CAUTION: SDK user should not call it directly, it is for internal use only.

#### Parameters
* `iotHubMessageHandle` Handle to the message. 

* `inputName` Pointer to the queue to input message to

#### Returns
Returns IOTHUB_MESSAGE_OK if the DiagnosticData was set successfully or an error code otherwise.

