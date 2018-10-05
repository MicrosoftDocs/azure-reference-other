# IoTHubModuleClient_LL_Destroy()

Disposes of resources allocated by the IoT Hub client. This is a blocking call.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_module_client_ll.h](../iot-c-ref-iothub-module-client-ll-h.md)"  
```C
void IoTHubModuleClient_LL_Destroy(
  IOTHUB_MODULE_CLIENT_LL_HANDLE  iotHubModuleClientHandle
);
```

## Parameters
* `iotHubModuleClientHandle` The handle created by a call to the create function.

