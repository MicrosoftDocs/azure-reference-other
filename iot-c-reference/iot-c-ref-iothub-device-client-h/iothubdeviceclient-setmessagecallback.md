# IoTHubDeviceClient_SetMessageCallback()

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_device_client.h](../iot-c-ref-iothub-device-client-h.md)"  

## Syntax

```C
IOTHUB_CLIENT_RESULT IoTHubDeviceClient_SetMessageCallback(
  IOTHUB_DEVICE_CLIENT_HANDLE           iotHubClientHandle,
  IOTHUB_CLIENT_MESSAGE_CALLBACK_ASYNC  messageCallback,
  void *                                userContextCallback
);
```

Sets up the message callback to be invoked when IoT Hub issues a message to the device. This is a blocking call.

## Parameters
* `iotHubClientHandle`The handle created by a call to the create function. 

* `messageCallback`The callback specified by the device for receiving messages from IoT Hub. 

* `userContextCallback`User specified context that will be provided to the callback. This can be `NULL`.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubDeviceClient_Destroy](#iothub__device__client_8h_1a2991e03140462e9cc1606ccf25e8b412) function from within any callback.

## Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

