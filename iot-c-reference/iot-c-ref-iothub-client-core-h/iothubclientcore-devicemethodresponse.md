# IoTHubClientCore_DeviceMethodResponse()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_client_core.h"](../iot-c-ref-iothub-client-core-h.md)  

## Syntax

```C
IOTHUB_CLIENT_RESULT IoTHubClientCore_DeviceMethodResponse(
  IOTHUB_CLIENT_CORE_HANDLE  iotHubClientHandle,
  METHOD_HANDLE              methodId,
  const unsigned char *      response,
  size_t                     response_size,
  int                        statusCode
);

```

