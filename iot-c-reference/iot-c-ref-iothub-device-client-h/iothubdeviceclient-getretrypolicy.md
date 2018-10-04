# IoTHubDeviceClient_GetRetryPolicy()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_device_client.h"](../iot-c-ref-iothub-device-client-h.md)  

## Syntax

```C
IOTHUB_CLIENT_RESULT IoTHubDeviceClient_GetRetryPolicy(
  IOTHUB_DEVICE_CLIENT_HANDLE	iotHubClientHandle,
  IOTHUB_CLIENT_RETRY_POLICY	retryPolicy,
  size_t *	retryTimeoutLimitInSeconds
);

```

Sets up the connection status callback to be invoked representing the status of the connection to IOT Hub. This is a blocking call.

#### Parameters
* `iotHubClientHandle` The handle created by a call to the create function. 

* `retryPolicy` Out parameter containing the policy to use to reconnect to IoT Hub. 

* `retryTimeoutLimitInSeconds` Out parameter containing maximum amount of time in seconds to attempt reconnection to IOT Hub.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubDeviceClient_LL_Destroy](#iothub__device__client__ll_8h_1ad2ac0d9176060dfeee0664668ce87e6f) function from within any callback.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

