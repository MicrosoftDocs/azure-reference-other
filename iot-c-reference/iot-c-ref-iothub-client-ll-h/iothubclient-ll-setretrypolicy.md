# IoTHubClient_LL_SetRetryPolicy()

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_client_ll.h](../iot-c-ref-iothub-client-ll-h.md)"  

## Syntax

```C
IOTHUB_CLIENT_RESULT IoTHubClient_LL_SetRetryPolicy(
  IOTHUB_CLIENT_LL_HANDLE     iotHubClientHandle,
  IOTHUB_CLIENT_RETRY_POLICY  retryPolicy,
  size_t                      retryTimeoutLimitInSeconds);
```

Sets up the connection status callback to be invoked representing the status of the connection to IOT Hub. This is a blocking call.

## Parameters
* `iotHubClientHandle`The handle created by a call to the create function. 

* `retryPolicy`The policy to use to reconnect to IoT Hub when a connection drops. 

* `retryTimeoutLimitInSeconds`Maximum amount of time(seconds) to attempt reconnection when a connection drops to IOT Hub.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubClient_LL_Destroy](#iothub__client__ll_8h_1afc3049dc24e311713ab4735873989a4a) function from within any callback.

## Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

