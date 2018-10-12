# IoTHubModuleClient_LL_DoWork()

This function is meant to be called by the user when work (sending/receiving) can be done by the IoTHubClient.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_module_client_ll.h](../iot-c-ref-iothub-module-client-ll-h.md)"  
```C
void IoTHubModuleClient_LL_DoWork(
  IOTHUB_MODULE_CLIENT_LL_HANDLE  iotHubModuleClientHandle
);
```

## Parameters
* `iotHubModuleClientHandle` The handle created by a call to the create function.

All IoTHubClient interactions (in regards to network traffic and/or user level callbacks) are the effect of calling this function and they take place synchronously inside _DoWork.

