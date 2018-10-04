# IoTHubClientCore_LL_SendReportedState()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_client_core_ll.h"](../iot-c-ref-iothub-client-core-ll-h.md)  

## Syntax

```C
IOTHUB_CLIENT_RESULT IoTHubClientCore_LL_SendReportedState(
  IOTHUB_CLIENT_CORE_LL_HANDLE           iotHubClientHandle,
  const unsigned char *                  reportedState,
  size_t                                 size,
  IOTHUB_CLIENT_REPORTED_STATE_CALLBACK  reportedStateCallback,
  void *                                 userContextCallback
);

```

