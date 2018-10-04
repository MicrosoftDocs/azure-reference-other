# IoTHubMessaging_LL_SetFeedbackMessageCallback()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_messaging_ll.h"](../iot-c-ref-iothub-messaging-ll-h.md)  

**[IOTHUB_MESSAGING_RESULT](#iothub__messaging__ll_8h_1ac5ac4fdc87db94cc7ddb7773e79290cd) [IoTHubMessaging_LL_SetFeedbackMessageCallback](#iothub__messaging__ll_8h_1a47226ad75e5373096c1783125ceb0f81)([IOTHUB_MESSAGING_HANDLE](#iothub__messaging__ll_8h_1ad4dd5cf65fd836ab5b053d59148343ff) messagingHandle,[IOTHUB_FEEDBACK_MESSAGE_RECEIVED_CALLBACK](#iothub__messaging__ll_8h_1a323b2eb492755a62424f130c7cb75888) feedbackMessageReceivedCallback,void * userContextCallback)**

This API specifies a callback to be used when the device receives the message.

#### Parameters
* `messagingClientHandle` The handle created by a call to the create function. 

* `feedbackMessageReceivedCallback` The callback specified by the user to be used for receiveng confirmation feedback from the deice about the recevied message.

* `userContextCallback` User specified context that will be provided to the callback. This can be `NULL`.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubMessaging_Destroy](#iothub__messaging_8h_1a5714171907353034b3bc60b7a404fc79) or IoTHubMessaging_Close function from within any callback.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

