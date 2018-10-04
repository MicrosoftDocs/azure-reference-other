# IoTHubDeviceClient_LL_SetConnectionStatusCallback()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_device_client_ll.h"](../iot-c-ref-iothub-device-client-ll-h.md)  

[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubDeviceClient_LL_SetConnectionStatusCallback`](#iothub__device__client__ll_8h_1a6d7da21562bfbcef5aa9d38503002bb2)(`[`IOTHUB_DEVICE_CLIENT_LL_HANDLE`](#iothub__device__client__ll_8h_1ab3ed1ccac784de53579181b349fd6616) iotHubClientHandle,`[`IOTHUB_CLIENT_CONNECTION_STATUS_CALLBACK`](#iothub__client__core__common_8h_1ad0d7e0712e620b1d55e72652f4f4f560) connectionStatusCallback,void * userContextCallback)`

Sets up the connection status callback to be invoked representing the status of the connection to IOT Hub. This is a blocking call.

#### Parameters
* `iotHubClientHandle` The handle created by a call to the create function. 

* `connectionStatusCallback` The callback specified by the device for receiving updates about the status of the connection to IoT Hub. 

* `userContextCallback` User specified context that will be provided to the callback. This can be `NULL`.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubDeviceClient_LL_Destroy](#iothub__device__client__ll_8h_1ad2ac0d9176060dfeee0664668ce87e6f) function from within any callback.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

