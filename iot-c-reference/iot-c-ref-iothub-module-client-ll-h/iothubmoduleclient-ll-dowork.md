# IoTHubModuleClient_LL_DoWork()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_module_client_ll.h"](../iot-c-ref-iothub-module-client-ll-h.md)  

**void [IoTHubModuleClient_LL_DoWork](#iothub__module__client__ll_8h_1a11c622cd616f20a3f4cdc10d48c1eac1)([IOTHUB_MODULE_CLIENT_LL_HANDLE](#iothub__module__client__ll_8h_1ae1a6187aacbdb56cde026ad3d228420a) iotHubModuleClientHandle)**

This function is meant to be called by the user when work (sending/receiving) can be done by the IoTHubClient.

#### Parameters
* `iotHubModuleClientHandle` The handle created by a call to the create function.

All IoTHubClient interactions (in regards to network traffic and/or user level callbacks) are the effect of calling this function and they take place synchronously inside _DoWork.

