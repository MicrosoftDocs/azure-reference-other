# IoTHubClient_SetConnectionStatusCallback()

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_client.h](../iot-c-ref-iothub-client-h.md)"  

## Syntax

```C
IOTHUB_CLIENT_RESULT IoTHubClient_SetConnectionStatusCallback(
  IOTHUB_CLIENT_HANDLE                      iotHubClientHandle,
  IOTHUB_CLIENT_CONNECTION_STATUS_CALLBACK  connectionStatusCallback,
  void *                                    userContextCallback);
```

Sets up the connection status callback to be invoked representing the status of the connection to IOT Hub. This is a blocking call.

## Parameters
* `iotHubClientHandle`The handle created by a call to the create function. 

* `connectionStatusCallback`The callback specified by the device for receiving updates about the status of the connection to IoT Hub. 

* `userContextCallback`User specified context that will be provided to the callback. This can be `NULL`.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubClient_LL_Destroy](#iothub__client__ll_8h_1afc3049dc24e311713ab4735873989a4a) function from within any callback.

## Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

