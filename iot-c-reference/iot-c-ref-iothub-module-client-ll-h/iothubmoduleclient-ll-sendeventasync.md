# IoTHubModuleClient_LL_SendEventAsync()

Asynchronous call to send the message specified by `eventMessageHandle`.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_module_client_ll.h](../iot-c-ref-iothub-module-client-ll-h.md)"  
```C
IOTHUB_CLIENT_RESULT IoTHubModuleClient_LL_SendEventAsync(
  IOTHUB_MODULE_CLIENT_LL_HANDLE             iotHubModuleClientHandle,
  IOTHUB_MESSAGE_HANDLE                      eventMessageHandle,
  IOTHUB_CLIENT_EVENT_CONFIRMATION_CALLBACK  eventConfirmationCallback,
  void *                                     userContextCallback
);
```

## Parameters
* `iotHubModuleClientHandle` The handle created by a call to the create function. 

* `eventMessageHandle` The handle to an IoT Hub message. 

* `eventConfirmationCallback` The callback specified by the module for receiving confirmation of the delivery of the IoT Hub message. This callback can be expected to invoke the [IoTHubModuleClient_LL_SendEventAsync](#iothub__module__client__ll_8h_1a51e76624cbf23f5538efc4bf705ba178) function for the same message in an attempt to retry sending a failing message. The user can specify a `NULL` value here to indicate that no callback is required. 

* `userContextCallback` User specified context that will be provided to the callback. This can be `NULL`.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubModuleClient_LL_Destroy](#iothub__module__client__ll_8h_1aad2dd6c3c24f89a9cfa861754a845138) function from within any callback.

## Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

