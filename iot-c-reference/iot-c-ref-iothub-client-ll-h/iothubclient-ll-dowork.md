# IoTHubClient_LL_DoWork()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_client_ll.h"](../iot-c-ref-iothub-client-ll-h.md)  

**void [IoTHubClient_LL_DoWork](#iothub__client__ll_8h_1af5e5e122bdc1f1228ae2116fc158b3d6)([IOTHUB_CLIENT_LL_HANDLE](#iothub__client__ll_8h_1abdbc7b1e6f374be8f2339d8c93f87742) iotHubClientHandle)**

This function is meant to be called by the user when work (sending/receiving) can be done by the IoTHubClient.

#### Parameters
* `iotHubClientHandle` The handle created by a call to the create function.

All IoTHubClient interactions (in regards to network traffic and/or user level callbacks) are the effect of calling this function and they take place synchronously inside _DoWork.

