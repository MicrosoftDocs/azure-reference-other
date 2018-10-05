# IoTHubModuleClient_Destroy()

Disposes of resources allocated by the IoT Hub client. This is a blocking call.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_module_client.h](../iot-c-ref-iothub-module-client-h.md)"  
```C
void IoTHubModuleClient_Destroy(
  IOTHUB_MODULE_CLIENT_HANDLE  iotHubModuleClientHandle
);
```

## Parameters
* `iotHubModuleClientHandle` The handle created by a call to the create function.

