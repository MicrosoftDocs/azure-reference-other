# IoTHubModuleClient_LL_GetLastMessageReceiveTime()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_module_client_ll.h"](../iot-c-ref-iothub-module-client-ll-h.md)  

**[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubModuleClient_LL_GetLastMessageReceiveTime](#iothub__module__client__ll_8h_1a179a3203b8865755dc8ac9fd9128b41e)([IOTHUB_MODULE_CLIENT_LL_HANDLE](#iothub__module__client__ll_8h_1ae1a6187aacbdb56cde026ad3d228420a) iotHubModuleClientHandle,time_t * lastMessageReceiveTime)**

This function returns in the out parameter `lastMessageReceiveTime` what was the value of the `time` function when the last message was received at the client.

#### Parameters
* `iotHubModuleClientHandle` The handle created by a call to the create function. 

* `lastMessageReceiveTime` Out parameter containing the value of `time` function when the last message was received.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

