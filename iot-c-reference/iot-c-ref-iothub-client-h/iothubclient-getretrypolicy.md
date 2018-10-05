# IoTHubClient_GetRetryPolicy()

Sets up the connection status callback to be invoked representing the status of the connection to IOT Hub. This is a blocking call.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_client.h](../iot-c-ref-iothub-client-h.md)"  
```C
IOTHUB_CLIENT_RESULT IoTHubClient_GetRetryPolicy(
  IOTHUB_CLIENT_HANDLE        iotHubClientHandle,
  IOTHUB_CLIENT_RETRY_POLICY  retryPolicy,
  size_t *                    retryTimeoutLimitInSeconds
);
```

## Parameters
* `iotHubClientHandle` The handle created by a call to the create function. 

* `retryPolicy` Out parameter containing the policy to use to reconnect to IoT Hub. 

* `retryTimeoutLimitInSeconds` Out parameter containing maximum amount of time in seconds to attempt reconnection to IOT Hub.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubClient_LL_Destroy](#iothub__client__ll_8h_1afc3049dc24e311713ab4735873989a4a) function from within any callback.

## Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

