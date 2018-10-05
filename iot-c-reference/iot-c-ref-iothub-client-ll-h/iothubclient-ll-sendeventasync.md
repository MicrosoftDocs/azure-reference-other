# IoTHubClient_LL_SendEventAsync()

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_client_ll.h](../iot-c-ref-iothub-client-ll-h.md)"  

## Syntax

```C
IOTHUB_CLIENT_RESULT IoTHubClient_LL_SendEventAsync(
  IOTHUB_CLIENT_LL_HANDLE                    iotHubClientHandle,

  IOTHUB_MESSAGE_HANDLE                      eventMessageHandle,

  IOTHUB_CLIENT_EVENT_CONFIRMATION_CALLBACK  eventConfirmationCallback,

  void *                                     userContextCallback
);
```

Asynchronous call to send the message specified by `eventMessageHandle`.

## Parameters
* **:iotHubClientHandle** The handle created by a call to the create function. 

* **:eventMessageHandle** The handle to an IoT Hub message. 

* **:eventConfirmationCallback** The callback specified by the device for receiving confirmation of the delivery of the IoT Hub message. This callback can be expected to invoke the [IoTHubClient_LL_SendEventAsync](#iothub__client__ll_8h_1ab47deec96944dd3f1bf0e747ab565277) function for the same message in an attempt to retry sending a failing message. The user can specify a `NULL` value here to indicate that no callback is required. 

* **:userContextCallback** User specified context that will be provided to the callback. This can be `NULL`.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubClient_LL_Destroy](#iothub__client__ll_8h_1afc3049dc24e311713ab4735873989a4a) function from within any callback.

## Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

