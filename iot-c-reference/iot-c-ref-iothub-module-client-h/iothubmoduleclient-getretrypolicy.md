# IoTHubModuleClient_GetRetryPolicy()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_module_client.h"](../iot-c-ref-iothub-module-client-h.md)  

**[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubModuleClient_GetRetryPolicy](#iothub__module__client_8h_1a96f0c8e7d91868a8919c0374918608c6)([IOTHUB_MODULE_CLIENT_HANDLE](#iothub__module__client_8h_1a61259310a513ae73b31cb3c66d3f4087) iotHubModuleClientHandle,[IOTHUB_CLIENT_RETRY_POLICY](#iothub__client__core__common_8h_1a361221e523247855ff0a05c2e2870e4a) * retryPolicy,size_t * retryTimeoutLimitInSeconds)**

Sets up the connection status callback to be invoked representing the status of the connection to IOT Hub. This is a blocking call.

#### Parameters
* `iotHubModuleClientHandle` The handle created by a call to the create function. 

* `retryPolicy` Out parameter containing the policy to use to reconnect to IoT Hub. 

* `retryTimeoutLimitInSeconds` Out parameter containing maximum amount of time in seconds to attempt reconnection to IOT Hub.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubModuleClient_LL_Destroy](#iothub__module__client__ll_8h_1aad2dd6c3c24f89a9cfa861754a845138) function from within any callback.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

