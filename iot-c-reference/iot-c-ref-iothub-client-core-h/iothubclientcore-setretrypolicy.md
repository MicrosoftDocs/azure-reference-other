# IoTHubClientCore_SetRetryPolicy()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_client_core.h"](../iot-c-ref-iothub-client-core-h.md)  

## Syntax

```C
IOTHUB_CLIENT_RESULT IoTHubClientCore_SetRetryPolicy(
  IOTHUB_CLIENT_CORE_HANDLE   iotHubClientHandle,
  IOTHUB_CLIENT_RETRY_POLICY  retryPolicy,
  size_t                      retryTimeoutLimitInSeconds
);

```

