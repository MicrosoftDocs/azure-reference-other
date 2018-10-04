# IoTHubMessaging_SetFeedbackMessageCallback()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_messaging.h"](../iot-c-ref-iothub-messaging-h.md)  

[`IOTHUB_MESSAGING_RESULT`](#iothub__messaging__ll_8h_1ac5ac4fdc87db94cc7ddb7773e79290cd) `[`IoTHubMessaging_SetFeedbackMessageCallback`](#iothub__messaging_8h_1a6c2c543c623b2bf45c6de7c2f6b07540)(`[`IOTHUB_MESSAGING_CLIENT_HANDLE`](#iothub__messaging_8h_1a388e756ded834589f37bbd04bf9cc9c0) messagingClientHandle,`[`IOTHUB_FEEDBACK_MESSAGE_RECEIVED_CALLBACK`](#iothub__messaging__ll_8h_1a323b2eb492755a62424f130c7cb75888) feedbackMessageReceivedCallback,void * userContextCallback)`

This API specifies a callback to be used when the device receives the message.

#### Parameters
* `messagingClientHandle` The handle created by a call to the create function. 

* `feedbackMessageReceivedCallback` The callback specified by the user to be used for receiveng confirmation feedback from the deice about the recevied message.

* `userContextCallback` User specified context that will be provided to the callback. This can be `NULL`.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubMessaging_Destroy](#iothub__messaging_8h_1a5714171907353034b3bc60b7a404fc79) or IoTHubMessaging_Close function from within any callback.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

