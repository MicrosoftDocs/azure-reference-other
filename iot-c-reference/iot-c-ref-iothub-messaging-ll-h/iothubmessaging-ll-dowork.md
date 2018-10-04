# IoTHubMessaging_LL_DoWork()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_messaging_ll.h"](../iot-c-ref-iothub-messaging-ll-h.md)  

void `[`IoTHubMessaging_LL_DoWork`](#iothub__messaging__ll_8h_1ad83618f43c1309edae5ab92f58abd4b5)(`[`IOTHUB_MESSAGING_HANDLE`](#iothub__messaging__ll_8h_1ad4dd5cf65fd836ab5b053d59148343ff) messagingHandle)`

This function is meant to be called by the user when work (sending/receiving) can be done by the IoTHubServiceClient.

#### Parameters
* `messagingHandle` The handle created by a call to the create function.

All IoTHubServiceClient interactions (in regards to network traffic and/or user level callbacks) are the effect of calling this function and they take place synchronously inside _DoWork.

