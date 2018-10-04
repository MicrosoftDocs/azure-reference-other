# IoTHubDeviceClient_LL_SetMessageCallback()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_device_client_ll.h"](../iot-c-ref-iothub-device-client-ll-h.md)  

[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubDeviceClient_LL_SetMessageCallback`](#iothub__device__client__ll_8h_1af8527e95987aa562dfbbf48482b78be1)(`[`IOTHUB_DEVICE_CLIENT_LL_HANDLE`](#iothub__device__client__ll_8h_1ab3ed1ccac784de53579181b349fd6616) iotHubClientHandle,`[`IOTHUB_CLIENT_MESSAGE_CALLBACK_ASYNC`](#iothub__client__core__common_8h_1adf7097e8fc9e34f26dd9347d4eaa5f8d) messageCallback,void * userContextCallback)`

Sets up the message callback to be invoked when IoT Hub issues a message to the device. This is a blocking call.

#### Parameters
* `iotHubClientHandle` The handle created by a call to the create function. 

* `messageCallback` The callback specified by the device for receiving messages from IoT Hub. 

* `userContextCallback` User specified context that will be provided to the callback. This can be `NULL`.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubDeviceClient_LL_Destroy](#iothub__device__client__ll_8h_1ad2ac0d9176060dfeee0664668ce87e6f) function from within any callback.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

