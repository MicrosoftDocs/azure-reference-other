# IoTHubModuleClient_LL_SetRetryPolicy()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_module_client_ll.h"](../iot-c-ref-iothub-module-client-ll-h.md)  

[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubModuleClient_LL_SetRetryPolicy`](#iothub__module__client__ll_8h_1ac59a75424dde5f3c9340bc8b8fbf61bb)(`[`IOTHUB_MODULE_CLIENT_LL_HANDLE`](#iothub__module__client__ll_8h_1ae1a6187aacbdb56cde026ad3d228420a) iotHubModuleClientHandle,`[`IOTHUB_CLIENT_RETRY_POLICY`](#iothub__client__core__common_8h_1a361221e523247855ff0a05c2e2870e4a) retryPolicy,size_t retryTimeoutLimitInSeconds)`

Sets up the connection status callback to be invoked representing the status of the connection to IOT Hub. This is a blocking call.

#### Parameters
* `iotHubModuleClientHandle` The handle created by a call to the create function. 

* `retryPolicy` The policy to use to reconnect to IoT Hub when a connection drops. 

* `retryTimeoutLimitInSeconds` Maximum amount of time(seconds) to attempt reconnection when a connection drops to IOT Hub.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubModuleClient_LL_Destroy](#iothub__module__client__ll_8h_1aad2dd6c3c24f89a9cfa861754a845138) function from within any callback.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

