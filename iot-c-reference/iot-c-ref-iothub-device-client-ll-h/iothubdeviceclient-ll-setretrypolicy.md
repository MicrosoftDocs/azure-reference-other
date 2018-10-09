# IoTHubDeviceClient_LL_SetRetryPolicy()

Sets up the connection status callback to be invoked representing the status of the connection to IOT Hub. This is a blocking call.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_device_client_ll.h](../iot-c-ref-iothub-device-client-ll-h.md)"  
```C
IOTHUB_CLIENT_RESULT IoTHubDeviceClient_LL_SetRetryPolicy(
  IOTHUB_DEVICE_CLIENT_LL_HANDLE  iotHubClientHandle,
  IOTHUB_CLIENT_RETRY_POLICY      retryPolicy,
  size_t                          retryTimeoutLimitInSeconds
);
```

## Parameters
* `iotHubClientHandle` The handle created by a call to the create function. 

* `retryPolicy` The policy to use to reconnect to IoT Hub when a connection drops. 

* `retryTimeoutLimitInSeconds` Maximum amount of time(seconds) to attempt reconnection when a connection drops to IOT Hub.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubDeviceClient_LL_Destroy](../iot-c-ref-iothub-device-client-ll-h/iothubdeviceclient-ll-destroy.md) function from within any callback.

## Return Value
IOTHUB_CLIENT_OK upon success or an error code upon failure.

