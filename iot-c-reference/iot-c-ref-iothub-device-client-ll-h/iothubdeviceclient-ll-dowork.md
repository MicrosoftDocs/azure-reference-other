# IoTHubDeviceClient_LL_DoWork()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_device_client_ll.h"](../iot-c-ref-iothub-device-client-ll-h.md)  

void `[`IoTHubDeviceClient_LL_DoWork`](#iothub__device__client__ll_8h_1a6e77da5502dff2bb43bace5173242f37)(`[`IOTHUB_DEVICE_CLIENT_LL_HANDLE`](#iothub__device__client__ll_8h_1ab3ed1ccac784de53579181b349fd6616) iotHubClientHandle)`

This function is meant to be called by the user when work (sending/receiving) can be done by the IoTHubClient.

#### Parameters
* `iotHubClientHandle` The handle created by a call to the create function.

All IoTHubClient interactions (in regards to network traffic and/or user level callbacks) are the effect of calling this function and they take place synchronously inside _DoWork.

