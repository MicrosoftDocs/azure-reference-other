# IoTHubModuleClient_SetMessageCallback()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_module_client.h"](../iot-c-ref-iothub-module-client-h.md)  

[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubModuleClient_SetMessageCallback`](#iothub__module__client_8h_1a74fa92ba8f75ae3022b01fe5ca9f7fb0)(`[`IOTHUB_MODULE_CLIENT_HANDLE`](#iothub__module__client_8h_1a61259310a513ae73b31cb3c66d3f4087) iotHubModuleClientHandle,`[`IOTHUB_CLIENT_MESSAGE_CALLBACK_ASYNC`](#iothub__client__core__common_8h_1adf7097e8fc9e34f26dd9347d4eaa5f8d) messageCallback,void * userContextCallback)`

Sets up the message callback to be invoked when IoT Hub issues a message to the device. This is a blocking call.

#### Parameters
* `iotHubModuleClientHandle` The handle created by a call to the create function. 

* `messageCallback` The callback specified by the device for receiving messages from IoT Hub. 

* `userContextCallback` User specified context that will be provided to the callback. This can be `NULL`.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubDeviceClient_Destroy](#iothub__device__client_8h_1a2991e03140462e9cc1606ccf25e8b412) function from within any callback.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

