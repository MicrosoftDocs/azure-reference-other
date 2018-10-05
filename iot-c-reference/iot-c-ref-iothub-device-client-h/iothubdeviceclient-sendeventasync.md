# IoTHubDeviceClient_SendEventAsync()

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_device_client.h](../iot-c-ref-iothub-device-client-h.md)"  

## Syntax

```C
IOTHUB_CLIENT_RESULT IoTHubDeviceClient_SendEventAsync(
  IOTHUB_DEVICE_CLIENT_HANDLE                iotHubClientHandle,

  IOTHUB_MESSAGE_HANDLE                      eventMessageHandle,

  IOTHUB_CLIENT_EVENT_CONFIRMATION_CALLBACK  eventConfirmationCallback,

  void *                                     userContextCallback
);
```

Asynchronous call to send the message specified by `eventMessageHandle`.

## Parameters
* **:iotHubClientHandle** The handle created by a call to the create function. 

* **:eventMessageHandle** The handle to an IoT Hub message. 

* **:eventConfirmationCallback** The callback specified by the device for receiving confirmation of the delivery of the IoT Hub message. This callback can be expected to invoke the [IoTHubDeviceClient_SendEventAsync](#iothub__device__client_8h_1a85fdfe3dface6a158db18bac7e21e296) function for the same message in an attempt to retry sending a failing message. The user can specify a `NULL` value here to indicate that no callback is required. 

* **:userContextCallback** User specified context that will be provided to the callback. This can be `NULL`.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubDeviceClient_Destroy](#iothub__device__client_8h_1a2991e03140462e9cc1606ccf25e8b412) function from within any callback.

## Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

