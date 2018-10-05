# IoTHubMessaging_LL_SetFeedbackMessageCallback()

\#include "[azure-iot-sdk-c/iothub_service_client/inc/iothub_messaging_ll.h](../iot-c-ref-iothub-messaging-ll-h.md)"  

## Syntax

```C
IOTHUB_MESSAGING_RESULT IoTHubMessaging_LL_SetFeedbackMessageCallback(
  IOTHUB_MESSAGING_HANDLE                    messagingHandle,
  IOTHUB_FEEDBACK_MESSAGE_RECEIVED_CALLBACK  feedbackMessageReceivedCallback,
  void *                                     userContextCallback);
```

This API specifies a callback to be used when the device receives the message.

## Parameters
* `messagingClientHandle`The handle created by a call to the create function. 

* `feedbackMessageReceivedCallback`The callback specified by the user to be used for receiveng confirmation feedback from the deice about the recevied message.

* `userContextCallback`User specified context that will be provided to the callback. This can be `NULL`.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubMessaging_Destroy](#iothub__messaging_8h_1a5714171907353034b3bc60b7a404fc79) or IoTHubMessaging_Close function from within any callback.

## Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

