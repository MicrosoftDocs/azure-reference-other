# IoTHubModuleClient_LL_GetRetryPolicy()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_module_client_ll.h"](../iot-c-ref-iothub-module-client-ll-h.md)  

## Syntax

```C
IOTHUB_CLIENT_RESULT IoTHubModuleClient_LL_GetRetryPolicy(
  IOTHUB_MODULE_CLIENT_LL_HANDLE  iotHubModuleClientHandle,
  IOTHUB_CLIENT_RETRY_POLICY      retryPolicy,
  size_t *                        retryTimeoutLimitInSeconds
);

```

Sets up the connection status callback to be invoked representing the status of the connection to IOT Hub. This is a blocking call.

#### Parameters
* `iotHubModuleClientHandle` The handle created by a call to the create function. 

* `retryPolicy` Out parameter containing the policy to use to reconnect to IoT Hub. 

* `retryTimeoutLimitInSeconds` Out parameter containing maximum amount of time in seconds to attempt reconnection to IOT Hub.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubModuleClient_LL_Destroy](#iothub__module__client__ll_8h_1aad2dd6c3c24f89a9cfa861754a845138) function from within any callback.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

