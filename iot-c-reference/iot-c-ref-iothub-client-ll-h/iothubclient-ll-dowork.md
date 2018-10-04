# IoTHubClient_LL_DoWork()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_client_ll.h"](../iot-c-ref-iothub-client-ll-h.md)  

## Syntax

```C
void IoTHubClient_LL_DoWork(
  IOTHUB_CLIENT_LL_HANDLE	iotHubClientHandle
);

```

This function is meant to be called by the user when work (sending/receiving) can be done by the IoTHubClient.

#### Parameters
* `iotHubClientHandle` The handle created by a call to the create function.

All IoTHubClient interactions (in regards to network traffic and/or user level callbacks) are the effect of calling this function and they take place synchronously inside _DoWork.

