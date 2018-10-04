# IoTHubDeviceClient_GetLastMessageReceiveTime()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_device_client.h"](../iot-c-ref-iothub-device-client-h.md)  

**[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubDeviceClient_GetLastMessageReceiveTime](#iothub__device__client_8h_1abc0085250813091a1e78fe4e07fa23ba)([IOTHUB_DEVICE_CLIENT_HANDLE](#iothub__device__client_8h_1ac0a6393bbcbec2e1b580e8c4c127f4c1) iotHubClientHandle,time_t * lastMessageReceiveTime)**

This function returns in the out parameter `lastMessageReceiveTime` what was the value of the `time` function when the last message was received at the client.

#### Parameters
* `iotHubClientHandle` The handle created by a call to the create function. 

* `lastMessageReceiveTime` Out parameter containing the value of `time` function when the last message was received.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

