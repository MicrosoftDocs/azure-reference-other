# IoTHubMessaging_LL_DoWork()

This function is meant to be called by the user when work (sending/receiving) can be done by the IoTHubServiceClient.

## Syntax

\#include "[azure-iot-sdk-c/iothub_service_client/inc/iothub_messaging_ll.h](../iot-c-ref-iothub-messaging-ll-h.md)"  
```C
void IoTHubMessaging_LL_DoWork(
  IOTHUB_MESSAGING_HANDLE  messagingHandle
);
```

## Parameters
* `messagingHandle` The handle created by a call to the create function.

All IoTHubServiceClient interactions (in regards to network traffic and/or user level callbacks) are the effect of calling this function and they take place synchronously inside _DoWork.

