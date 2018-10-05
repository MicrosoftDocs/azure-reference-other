# IoTHubClientCore_LL_GetRetryPolicy()

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_client_core_ll.h](../iot-c-ref-iothub-client-core-ll-h.md)"  

## Syntax

```C
IOTHUB_CLIENT_RESULT IoTHubClientCore_LL_GetRetryPolicy(
  IOTHUB_CLIENT_CORE_LL_HANDLE  iotHubClientHandle,

  IOTHUB_CLIENT_RETRY_POLICY    retryPolicy,

  size_t *                      retryTimeoutLimitInSeconds
);
```

