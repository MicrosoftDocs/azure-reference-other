# IoTHubModuleClient_SendEventToOutputAsync()

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_module_client.h](../iot-c-ref-iothub-module-client-h.md)"  

## Syntax

```C
IOTHUB_CLIENT_RESULT IoTHubModuleClient_SendEventToOutputAsync(
  IOTHUB_MODULE_CLIENT_HANDLE                iotHubModuleClientHandle,
  IOTHUB_MESSAGE_HANDLE                      eventMessageHandle,
  const char *                               outputName,
  IOTHUB_CLIENT_EVENT_CONFIRMATION_CALLBACK  eventConfirmationCallback,
  void *                                     userContextCallback);
```

Asynchronous call to send the message specified by `eventMessageHandle`.

## Parameters
* `iotHubModuleClientHandle`The handle created by a call to the create function. 

* `eventMessageHandle`The handle to an IoT Hub message. 

* `outputName`The name of the queue to send the message to. 

* `eventConfirmationCallback`The callback specified by the module for receiving confirmation of the delivery of the IoT Hub message. This callback can be expected to invoke the [IoTHubClient_SendEventAsync](#iothub__client_8h_1a3e60e953d03a503c1ae30dd6af7f390f) function for the same message in an attempt to retry sending a failing message. The user can specify a `NULL` value here to indicate that no callback is required. 

* `userContextCallback`User specified context that will be provided to the callback. This can be `NULL`.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubClient_Destroy](#iothub__client_8h_1a47fce212d1c5026e02ccd670242e1d83) function from within any callback.

## Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

