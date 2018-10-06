# IoTHubMessaging_SetFeedbackMessageCallback()

This API specifies a callback to be used when the device receives the message.

## Syntax

\#include "[azure-iot-sdk-c/iothub_service_client/inc/iothub_messaging.h](../iot-c-ref-iothub-messaging-h.md)"  
```C
IOTHUB_MESSAGING_RESULT IoTHubMessaging_SetFeedbackMessageCallback(
  IOTHUB_MESSAGING_CLIENT_HANDLE             messagingClientHandle,
  IOTHUB_FEEDBACK_MESSAGE_RECEIVED_CALLBACK  feedbackMessageReceivedCallback,
  void *                                     userContextCallback
);
```

## Parameters
* `messagingClientHandle` The handle created by a call to the create function. 

* `feedbackMessageReceivedCallback` The callback specified by the user to be used for receiveng confirmation feedback from the deice about the recevied message.

* `userContextCallback` User specified context that will be provided to the callback. This can be `NULL`.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubMessaging_Destroy](#undefined) or IoTHubMessaging_Close function from within any callback.

## Return Value
IOTHUB_CLIENT_OK upon success or an error code upon failure.

