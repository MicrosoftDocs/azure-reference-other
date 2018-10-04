# IoTHubDeviceClient_GetRetryPolicy()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_device_client.h"](../iot-c-ref-iothub-device-client-h.md)  

**[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubDeviceClient_GetRetryPolicy](#iothub__device__client_8h_1a7e001ad2e02069d7b9773f8f245fae77)([IOTHUB_DEVICE_CLIENT_HANDLE](#iothub__device__client_8h_1ac0a6393bbcbec2e1b580e8c4c127f4c1) iotHubClientHandle,[IOTHUB_CLIENT_RETRY_POLICY](#iothub__client__core__common_8h_1a361221e523247855ff0a05c2e2870e4a) * retryPolicy,size_t * retryTimeoutLimitInSeconds)**

Sets up the connection status callback to be invoked representing the status of the connection to IOT Hub. This is a blocking call.

#### Parameters
* `iotHubClientHandle` The handle created by a call to the create function. 

* `retryPolicy` Out parameter containing the policy to use to reconnect to IoT Hub. 

* `retryTimeoutLimitInSeconds` Out parameter containing maximum amount of time in seconds to attempt reconnection to IOT Hub.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubDeviceClient_LL_Destroy](#iothub__device__client__ll_8h_1ad2ac0d9176060dfeee0664668ce87e6f) function from within any callback.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

