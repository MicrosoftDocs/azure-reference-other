# IoTHubModuleClient_Destroy()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_module_client.h"](../iot-c-ref-iothub-module-client-h.md)  

## Syntax

```C
void IoTHubModuleClient_Destroy(
  IOTHUB_MODULE_CLIENT_HANDLE	iotHubModuleClientHandle
);

```

Disposes of resources allocated by the IoT Hub client. This is a blocking call.

#### Parameters
* `iotHubModuleClientHandle` The handle created by a call to the create function.

