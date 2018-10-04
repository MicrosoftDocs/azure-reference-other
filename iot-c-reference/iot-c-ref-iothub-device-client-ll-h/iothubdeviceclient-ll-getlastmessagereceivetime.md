# IoTHubDeviceClient_LL_GetLastMessageReceiveTime()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_device_client_ll.h"](../iot-c-ref-iothub-device-client-ll-h.md)  

[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubDeviceClient_LL_GetLastMessageReceiveTime`](#iothub__device__client__ll_8h_1a04d8f5acf6f66f0075e5febc4a43695c)(`[`IOTHUB_DEVICE_CLIENT_LL_HANDLE`](#iothub__device__client__ll_8h_1ab3ed1ccac784de53579181b349fd6616) iotHubClientHandle,time_t * lastMessageReceiveTime)`

This function returns in the out parameter `lastMessageReceiveTime` what was the value of the `time` function when the last message was received at the client.

#### Parameters
* `iotHubClientHandle` The handle created by a call to the create function. 

* `lastMessageReceiveTime` Out parameter containing the value of `time` function when the last message was received.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

