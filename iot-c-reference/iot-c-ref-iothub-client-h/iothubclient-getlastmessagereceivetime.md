# IoTHubClient_GetLastMessageReceiveTime()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_client.h"](../iot-c-ref-iothub-client-h.md)  

**[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClient_GetLastMessageReceiveTime](#iothub__client_8h_1a4484e3db3c295c66d379b44fc53cfd79)([IOTHUB_CLIENT_HANDLE](#iothub__client_8h_1a228b1409767f2560aa0724caad86fd6d) iotHubClientHandle,time_t * lastMessageReceiveTime)**

This function returns in the out parameter `lastMessageReceiveTime` what was the value of the `time` function when the last message was received at the client.

#### Parameters
* `iotHubClientHandle` The handle created by a call to the create function. 

* `lastMessageReceiveTime` Out parameter containing the value of `time` function when the last message was received.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

