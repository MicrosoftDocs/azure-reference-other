# IoTHubModuleClient_GetLastMessageReceiveTime()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_module_client.h"](../iot-c-ref-iothub-module-client-h.md)  

**[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubModuleClient_GetLastMessageReceiveTime](#iothub__module__client_8h_1a8547bb5912b9c29906527dcce9cd890c)([IOTHUB_MODULE_CLIENT_HANDLE](#iothub__module__client_8h_1a61259310a513ae73b31cb3c66d3f4087) iotHubModuleClientHandle,time_t * lastMessageReceiveTime)**

This function returns in the out parameter `lastMessageReceiveTime` what was the value of the `time` function when the last message was received at the client.

#### Parameters
* `iotHubModuleClientHandle` The handle created by a call to the create function. 

* `lastMessageReceiveTime` Out parameter containing the value of `time` function when the last message was received.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

